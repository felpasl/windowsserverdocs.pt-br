---
title: Introdução a contas de serviços gerenciados de grupo
description: Segurança do Windows Server
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: security-gmsa
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 7130ad73-9688-4f64-aca1-46a9187a46cf
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/12/2016
ms.openlocfilehash: 45fe605228189f49d40543e5da703f9afe0d962e
ms.sourcegitcommit: 4a03f263952c993dfdf339dd3491c73719854aba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74791201"
---
# <a name="getting-started-with-group-managed-service-accounts"></a>Introdução a contas de serviços gerenciados de grupo

>Aplicável ao: Windows Server (canal semestral), Windows Server 2016


Este guia fornece instruções passo a passo e informações básicas para habilitar e usar contas de serviço gerenciado de grupo no Windows Server 2012.

**Neste documento**

-   [Pré-requisitos](#BKMK_Prereqs)

-   [Introdução](#BKMK_Intro)

-   [Implantando um novo farm de servidores](#BKMK_DeployNewFarm)

-   [Adicionando hosts membros a um farm de servidores existente](#BKMK_AddMemberHosts)

-   [Atualizando as propriedades da conta de serviço gerenciado de grupo](#BKMK_Update_gMSA)

-   [Descomissionando hosts membros de um farm de servidores existente](#BKMK_DecommMemberHosts)


> [!NOTE]
> Este tópico inclui cmdlets do Windows PowerShell de exemplo que podem ser usados para automatizar alguns dos procedimentos descritos. Para obter mais informações, consulte [Usando cmdlets](https://go.microsoft.com/fwlink/p/?linkid=230693).

## <a name="BKMK_Prereqs"></a>Pré-requisitos
Consulte a seção neste tópico sobre [Requisitos para as Contas de Serviço Gerenciado de grupo](#BKMK_gMSA_Req).

## <a name="BKMK_Intro"></a>Apresentações
Quando um computador cliente se conecta a um serviço hospedado em um farm de servidores que usa NLB (balanceamento de carga de rede) ou algum outro método em que, para o cliente, todos os servidores parecem ser o mesmo serviço; os protocolos de autenticação que dão suporte à autenticação mútua, tal como o Kerberos, não podem ser usados, a menos que todas as instâncias dos serviços usem a mesma entidade. Isso significa que cada serviço tem que usar as mesmas senhas/chaves para provar sua identidade.

> [!NOTE]
> Os clusters de failover não dão suporte a gMSAs. No entanto, os serviços que são executados sobre o Serviço de cluster poderão usar uma gMSA ou uma sMSA, se forem um serviço Windows, um pool de aplicativos, uma tarefa agendada ou oferecerem suporte nativo a gMSA ou sMSA.

Os serviços têm as entidades a seguir entre as quais escolher, e cada uma delas apresenta determinadas limitações.

|Entidades|Escopo|Serviços com suporte|Gerenciamento de senhas|
|-------|-----|-----------|------------|
|Conta de Computador do sistema do Windows|Domínio|Limitado a um servidor ingressado no domínio|O computador gerencia|
|Conta de Computador sem o sistema do Windows|Domínio|Qualquer servidor ingressado no domínio|Nenhuma|
|Conta Virtual|Local|Limitado a um servidor|O computador gerencia|
|Conta de Serviço Gerenciado independente do Windows 7|Domínio|Limitado a um servidor ingressado no domínio|O computador gerencia|
|Conta de Usuário|Domínio|Qualquer servidor ingressado no domínio|Nenhuma|
|Contas de serviço gerenciadas por grupo|Domínio|Qualquer servidor ingressado no domínio do Windows Server 2012|O controlador de domínio gerencia e o host recupera|

Uma conta de computador do Windows, uma sMSA (Conta de Serviço Gerenciado independente) do Windows 7 ou contas virtuais não podem ser compartilhadas em diversos sistemas. Se você configurasse uma conta para serviços em farms de servidores a serem compartilhados, teria que escolher uma conta de usuário ou uma conta de computador separada do sistema do Windows. De qualquer maneira, essas contas não têm a funcionalidade de gerenciamento de senhas de ponto único de controle. Isso cria um problema em que cada organização precisa criar uma solução dispendiosa para atualizar chaves do serviço no Active Directory e distribuir as chaves a todas as instâncias desses serviços.

Com o Windows Server 2012, serviços ou administradores de serviço não precisam gerenciar a sincronização de senha entre instâncias de serviço ao usar contas de serviço gerenciado de grupo (gMSA). Você provisiona a gMSA no AD e configura os serviços que dão suporte a Contas de Serviço Gerenciado. Você pode provisionar uma gMSA usando os cmdlets *-ADServiceAccount que fazem parte do módulo do Active Directory. A configuração de identidade do serviço no host tem suporte por:

-   Algumas APIs, como sMSA, portanto, produtos que dão suporte a sMSA oferecerão suporte a gMSA

-   Serviços que usam o Gerenciador de Controle de Serviço para configurar a identidade de logon

-   Serviços que usam o gerenciador do IIS em pools de aplicativos para configurar identidade

-   Tarefas que usam o Agendador de Tarefas.

### <a name="BKMK_gMSA_Req"></a>Requisitos para contas de serviço gerenciado de grupo
A tabela a seguir lista os requisitos de sistema operacional para a autenticação Kerberos funcionar com serviços que usam gMSA. Os requisitos do Active Directory estão listados após a tabela.

Uma arquitetura de 64 bits é necessária para executar os comandos do Windows PowerShell usados para administrar as Contas de Serviço Gerenciado de grupo.

**Requisitos do sistema operacional**

|Elemento|Requisito|Sistema operacional|
|------|--------|----------|
|Host de Aplicativo Cliente|Cliente Kerberos compatível com RFC|Pelo menos Windows XP|
|DCs de domínio da conta do usuário|KDC compatível com RFC|Pelo menos Windows Server 2003|
|Hosts membros de serviço compartilhado|| Windows Server 2012 |
|Controladores de domínio do host membro|KDC compatível com RFC|Pelo menos Windows Server 2003|
|Controladores de domínio da conta do gMSA| DCs do Windows Server 2012 disponíveis para o host recuperarem a senha|Domínio com o Windows Server 2012 que pode ter alguns sistemas anteriores ao Windows Server 2012 |
|Host de serviço back-end|Servidor de aplicativos Kerberos compatível com RFC|Pelo menos Windows Server 2003|
|Controladores de domínio da conta do serviço de back-end|KDC compatível com RFC|Pelo menos Windows Server 2003|
|Windows PowerShell para Active Directory|Windows PowerShell para Active Directory instalado localmente em um computador que dê suporte a uma arquitetura de 64 bits ou em seu computador de gerenciamento remoto (por exemplo, usando o Remote Server Administration Toolkit)| Windows Server 2012 |

**Requisitos de serviço de Domínio do Active Directory**

-   O esquema de Active Directory na floresta do domínio gMSA precisa ser atualizado para o Windows Server 2012 para criar um gMSA.

    Você pode atualizar o esquema instalando um controlador de domínio que executa o Windows Server 2012 ou executando a versão do adprep. exe de um computador que executa o Windows Server 2012. O valor de atributo de versão do objeto para o objeto CN=Schema,CN=Configuration,DC=Contoso,DC=Com deve ser 52.

-   Nova conta gMSA provisionada

-   Se você estiver gerenciando a permissão de host do serviço para usar a gMSA por grupo, o grupo de segurança novo ou existente

-   Se estiver gerenciando o controle de acesso ao serviço por grupo, o grupo de segurança novo ou existente

-   Se a primeira chave raiz mestra do Active Directory não estiver implantada no domínio ou não tiver sido criada, crie-a. O resultado dessa criação pode ser verificado no log Operacional KdsSvc, ID de Evento 4004.

Para obter instruções sobre como criar a chave, consulte [criar a chave de raiz KDS dos serviços de distribuição de chaves](create-the-key-distribution-services-kds-root-key.md). A chave raiz do Serviço de Distribuição de Chave da Microsoft (kdssvc.dll) do AD.

**Lifecycle**

O ciclo de vida de um farm de servidores que usa um recurso de gMSA geralmente envolve as seguintes tarefas:

-   Implantando um novo farm de servidores

-   Adicionando hosts membros a um farm de servidores existente

-   Encerrando hosts membros em um farm de servidores existente

-   Encerrando um farm de servidores existente

-   Removendo um host membro comprometido de um farm de servidores, se necessário.

## <a name="BKMK_DeployNewFarm"></a>Implantando um novo farm de servidores
Ao implantar um novo farm de servidores, o administrador de serviço precisará determinar:

-   Se o serviço dá suporte ao uso de gMSAs

-   Se o serviço requer conexões autenticadas de entrada ou de saída

-   Os nomes de conta do computador dos hosts membros para o serviço que usa a gMSA

-   O nome NetBIOS para o serviço

-   O nome de host DNS para o serviço

-   Os SPNs (Nomes da Entidades de Serviço) para o serviço

-   O intervalo de alteração de senha (o padrão é 30 dias).

### <a name="BKMK_Step1"></a>Etapa 1: provisionando contas de serviço gerenciado de grupo
Você pode criar um gMSA somente se o esquema de floresta foi atualizado para o Windows Server 2012, a chave raiz mestra para Active Directory foi implantada e há pelo menos um Windows Server 2012 DC no domínio no qual o gMSA será criado.

A associação em **Admins. do Domínio**, **Opers. de Contas** ou a capacidade de criar objetos msDS-GroupManagedServiceAccount é o mínimo necessário para concluir os procedimentos a seguir.

#### <a name="BKMK_CreateGMSA"></a>Para criar um gMSA usando o cmdlet New-ADServiceAccount

1.  No controlador de domínio do Windows Server 2012, execute o Windows PowerShell na barra de tarefas.

2.  No prompt de comando do Windows PowerShell, digite os comandos a seguir e pressione ENTER. (O módulo Active Directory será carregado automaticamente.)

    **New-ADServiceAccount [-name] <string>-DNSHostName <string> [-KerberosEncryptionType <ADKerberosEncryptionType>] [-ManagedPasswordIntervalInDays < Nullable [Int32] >] [-PrincipalsAllowedToRetrieveManagedPassword < ADPrincipal [] >]-SamAccountName <string>-Serviceprincipalnamename < String [] >**

    |Parâmetro|Cadeia de caracteres|Exemplo|
    |-------|-----|------|
    |Nome|Nome da conta|ITFarm1|
    |DNSHostName|Nome de host DNS do serviço|ITFarm1.contoso.com|
    |KerberosEncryptionType|Quaisquer tipos de criptografia com suporte pelos servidores host|RC4, AES128, AES256|
    |ManagedPasswordIntervalInDays|Intervalo de alteração de senha em dias (o padrão é 30 dias, se nenhum tiver sido fornecido)|90|
    |PrincipalsAllowedToRetrieveManagedPassword|As contas de computador dos hosts membros ou o grupo de segurança dos quais os hosts membros fazem parte|ITFarmHosts|
    |SamAccountName|Nome NetBIOS para o serviço, se não for igual a Nome|ITFarm1|
    |ServicePrincipalNames|SPNs (Nomes da entidade de serviço) para o serviço|http/ITFarm1.contoso.com/contoso.com, http/ITFarm1.contoso.com/contoso, http/ITFarm1/contoso.com, http/ITFarm1/contoso|

    > [!IMPORTANT]
    > O intervalo de alteração de senha só pode ser configurado durante a criação. Se for necessário alterar o intervalo, crie uma nova gMSA e configure-a no momento da criação.

    **Exemplo**

    Insira o comando em uma única linha, mesmo se houver quebra automática de linha em várias linhas devido a restrições de formatação.

    ```Powershell
    New-ADServiceAccount ITFarm1 -DNSHostName ITFarm1.contoso.com -PrincipalsAllowedToRetrieveManagedPassword ITFarmHosts$ -KerberosEncryptionType RC4, AES128, AES256 -ServicePrincipalNames http/ITFarm1.contoso.com/contoso.com, http/ITFarm1.contoso.com/contoso, http/ITFarm1/contoso.com, http/ITFarm1/contoso
    ```

A associação em **Admins. do Domínio**, **Opers. de Contas** ou a capacidade de criar objetos de msDS-GroupManagedServiceAccount é o mínimo necessário para concluir esse procedimento. Para obter informações detalhadas sobre como usar as contas e as associações a grupos apropriadas, consulte [Grupos padrão Local e Domínio](https://technet.microsoft.com/library/dd728026(WS.10).aspx).

##### <a name="to-create-a-gmsa-for-outbound-authentication-only-using-the-new-adserviceaccount-cmdlet"></a>Para criar uma gMSA para autenticação de saída usando apenas o cmdlet New-ADServiceAccount

1.  No controlador de domínio do Windows Server 2012, execute o Windows PowerShell na barra de tarefas.

2.  No prompt de comando do módulo Active Directory do Windows PowerShell, digite os seguintes comandos e pressione ENTER:

    **New-ADServiceAccount [-name] <string>-RestrictToOutboundAuthenticationOnly [-ManagedPasswordIntervalInDays < Nullable [Int32] >] [-PrincipalsAllowedToRetrieveManagedPassword < ADPrincipal [] >]**

    |Parâmetro|Cadeia de caracteres|Exemplo|
    |-------|-----|------|
    |Nome|Nome da conta|ITFarm1|
    |ManagedPasswordIntervalInDays|Intervalo de alteração de senha em dias (o padrão é 30 dias, se nenhum tiver sido fornecido)|75|
    |PrincipalsAllowedToRetrieveManagedPassword|As contas de computador dos hosts membros ou o grupo de segurança dos quais os hosts membros fazem parte|ITFarmHosts|

    > [!IMPORTANT]
    > O intervalo de alteração de senha só pode ser configurado durante a criação. Se for necessário alterar o intervalo, crie uma nova gMSA e configure-a no momento da criação.

**Exemplo**

```PowerShell
New-ADServiceAccount ITFarm1 -RestrictToOutboundAuthenticationOnly - PrincipalsAllowedToRetrieveManagedPassword ITFarmHosts$
```

### <a name="BKMK_ConfigureServiceIdentity"></a>Etapa 2: Configurando o serviço de aplicativo de identidade de serviço
Para configurar os serviços no Windows Server 2012, consulte a seguinte documentação de recurso:

-   Pool de aplicativos do IIS

    Para obter mais informações, consulte [Especificar uma identidade para um pool de aplicativos (IIS 7)](https://technet.microsoft.com/library/cc771170(WS.10).aspx).

-   Serviços Windows

    Para obter mais informações, consulte [Serviços](https://technet.microsoft.com/library/cc772408.aspx).

-   Tarefas

    Para obter mais informações, consulte [Visão geral sobre o Agendador de Tarefas](https://technet.microsoft.com/library/cc721871.aspx).

Outros serviços poderiam dar suporte a gMSA. Consulte a documentação de produto apropriada para obter detalhes sobre como configurar esses serviços.

## <a name="BKMK_AddMemberHosts"></a>Adicionando hosts membros a um farm de servidores existente
Se estiver usando grupos de segurança para gerenciar hosts membros, adicione a conta de computador do novo host membro ao grupo de segurança (que os hosts membros do gMSA são membros) usando um dos métodos a seguir.

A associação em **Admins. do Domínio**ou a capacidade de adicionar membros ao objeto de grupo de segurança é o mínimo necessário para concluir esses procedimentos.

-   Método 1: Usuários e computadores do Active Directory

    Para obter os procedimentos sobre como usar o método, consulte [Adicionar uma conta de computador a um grupo](https://technet.microsoft.com/library/cc733097.aspx) usando a interface do Windows e [Gerenciar diferentes domínios no Centro Administrativo do Active Directory](manage-different-domains-in-active-directory-administrative-center.md).

-   Método 2: dsmod

    Para obter os procedimentos sobre como usar o método, consulte [Adicionar uma conta de computador a um grupo](https://technet.microsoft.com/library/cc733097.aspx) usando a linha de comando.

-   Método 3: cmdlet Active Directory Add-ADPrincipalGroupMembership do Windows PowerShell

    Para obter os procedimentos sobre como usar o método, consulte [Add-ADPrincipalGroupMembership](https://technet.microsoft.com/library/ee617203.aspx).

Se estiver usando contas de computador, localize as contas existentes e adicione a nova conta de computador.

A associação em **Admins. do Domínio**, **Opers. de Contas**ou a capacidade de gerenciar objetos de msDS-GroupManagedServiceAccount é o mínimo necessário para concluir esse procedimento. Para obter informações detalhadas sobre como usar as contas e as associações a grupos apropriadas, consulte Grupos padrão Local e Domínio.

#### <a name="to-add-member-hosts-using-the-set-adserviceaccount-cmdlet"></a>Para adicionar hosts membros usando o cmdlet Set-ADServiceAccount

1.  No controlador de domínio do Windows Server 2012, execute o Windows PowerShell na barra de tarefas.

2.  No prompt de comando do módulo Active Directory do Windows PowerShell, digite os seguintes comandos e pressione ENTER:

    **Get-ADServiceAccount [-name] <string>-PrincipalsAllowedToRetrieveManagedPassword**

3.  No prompt de comando do módulo Active Directory do Windows PowerShell, digite os seguintes comandos e pressione ENTER:

    **Set-ADServiceAccount [-name] <string>-PrincipalsAllowedToRetrieveManagedPassword < ADPrincipal [] >**

|Parâmetro|Cadeia de caracteres|Exemplo|
|-------|-----|------|
|Nome|Nome da conta|ITFarm1|
|PrincipalsAllowedToRetrieveManagedPassword|As contas de computador dos hosts membros ou o grupo de segurança dos quais os hosts membros fazem parte|Host1, Host2, Host3|

**Exemplo**

Por exemplo, para adicionar hosts membros, digite os comandos a seguir e pressione ENTER.

```PowerShell
Get-ADServiceAccount [-Name] ITFarm1 -PrincipalsAllowedToRetrieveManagedPassword
```

```PowerShell
Set-ADServiceAccount [-Name] ITFarm1 -PrincipalsAllowedToRetrieveManagedPassword Host1$,Host2$,Host3$
```

## <a name="BKMK_Update_gMSA"></a>Atualizando as propriedades da conta de serviço gerenciado de grupo
A associação em **Admins. do Domínio**, **Opers. de Contas**ou a capacidade de gravar em objetos msDS-GroupManagedServiceAccount é o mínimo necessário para concluir esses procedimentos.

Abra o Módulo Active Directory do Windows PowerShell e configure qualquer propriedade usando o cmdlet Set-ADServiceAccount.

Para obter informações detalhadas sobre como configurar essas propriedades, consulte [Set-ADServiceAccount](https://technet.microsoft.com/library/ee617252.aspx) na Biblioteca do TechNet ou digite **Get-Help Set-ADServiceAccount** no prompt de comando do módulo Active Directory para Windows PowerShell e pressione ENTER.

## <a name="BKMK_DecommMemberHosts"></a>Descomissionando hosts membros de um farm de servidores existente
A associação em **Admins. do Domínio** ou a capacidade de remover membros do objeto de grupo de segurança é o mínimo necessário para concluir esses procedimentos.

### <a name="step-1-remove-member-host-from-gmsa"></a>Etapa 1: remover host membro da gMSA
Se estiver usando grupos de segurança para gerenciar hosts membros, remova a conta de computador do host do membro descomissionado do grupo de segurança ao qual os hosts membros do gMSA são membros usando qualquer um dos métodos a seguir.

-   Método 1: Usuários e computadores do Active Directory

    Para obter os procedimentos sobre como usar o método, consulte [Excluir uma conta de computador](https://technet.microsoft.com/library/cc754624.aspx) usando a interface do Windows e [Gerenciar diferentes domínios no Centro Administrativo do Active Directory](manage-different-domains-in-active-directory-administrative-center.md).

-   Método 2: drsm

    Para obter os procedimentos sobre como usar o método, consulte [Excluir uma conta de computador](https://technet.microsoft.com/library/cc754624.aspx) usando a linha de comando.

-   Método 3: cmdlet Active Directory Remove-ADPrincipalGroupMembership do Windows PowerShell

    Para obter informações detalhadas sobre como fazer isso, consulte  [Remove-ADPrincipalGroupMembership](https://technet.microsoft.com/library/ee617243.aspx) na Biblioteca do TechNet ou digite **Get-Help Remove-ADPrincipalGroupMembership** no prompt de comando do módulo Active Directory para Windows PowerShell e pressione ENTER.

Se estiver listando contas de computador, recupere as contas existentes e adicione todas, exceto a conta de computador removida.

A associação em **Admins. do Domínio**, **Opers. de Contas**ou a capacidade de gerenciar objetos de msDS-GroupManagedServiceAccount é o mínimo necessário para concluir esse procedimento. Para obter informações detalhadas sobre como usar as contas e as associações a grupos apropriadas, consulte Grupos padrão Local e Domínio.

##### <a name="to-remove-member-hosts-using-the-set-adserviceaccount-cmdlet"></a>Para remover hosts membros usando o cmdlet Set-ADServiceAccount

1.  No controlador de domínio do Windows Server 2012, execute o Windows PowerShell na barra de tarefas.

2.  No prompt de comando do módulo Active Directory do Windows PowerShell, digite os seguintes comandos e pressione ENTER:

    **Get-ADServiceAccount [-name] <string>-PrincipalsAllowedToRetrieveManagedPassword**

3.  No prompt de comando do módulo Active Directory do Windows PowerShell, digite os seguintes comandos e pressione ENTER:

    **Set-ADServiceAccount [-name] <string>-PrincipalsAllowedToRetrieveManagedPassword < ADPrincipal [] >**

|Parâmetro|Cadeia de caracteres|Exemplo|
|-------|-----|------|
|Nome|Nome da conta|ITFarm1|
|PrincipalsAllowedToRetrieveManagedPassword|As contas de computador dos hosts membros ou o grupo de segurança dos quais os hosts membros fazem parte|Host1, Host3|

**Exemplo**

Por exemplo, para remover hosts membros, digite os comandos a seguir e pressione ENTER.

```PowerShell
Get-ADServiceAccount [-Name] ITFarm1 -PrincipalsAllowedToRetrieveManagedPassword
```

```PowerShell
Set-ADServiceAccount [-Name] ITFarm1 -PrincipalsAllowedToRetrieveManagedPassword Host1$,Host3$
```

### <a name="BKMK_RemoveGMSA"></a>Etapa 2: removendo uma conta de serviço gerenciado de grupo do sistema
Remover as credenciais da gMSA armazenadas em cache do host membro usando a API Uninstall-ADServiceAccount ou NetRemoveServiceAccount no sistema host.

A associação em **Administradores** ou equivalente é o mínimo necessário para concluir esses procedimentos.

##### <a name="to-remove-a-gmsa-using-the-uninstall-adserviceaccount-cmdlet"></a>Para remover uma gMSA usando o cmdlet Uninstall-ADServiceAccount

1.  No controlador de domínio do Windows Server 2012, execute o Windows PowerShell na barra de tarefas.

2.  No prompt de comando do módulo Active Directory do Windows PowerShell, digite os seguintes comandos e pressione ENTER:

    **Uninstall-ADServiceAccount < ADServiceAccount >**

    **Exemplo**

    Por exemplo, para remover as credenciais armazenadas em cache para uma gMSA denominada ITFarm1, digite o seguinte comando e pressione ENTER:

    ```PowerShell
    Uninstall-ADServiceAccount ITFarm1
    ```

Para obter mais informações sobre o cmdlet Uninstall-ADServiceAccount, no prompt de comando do módulo Active Directory para Windows PowerShell, digite **Get-Help Uninstall-ADServiceAccount**e pressione ENTER ou consulte as informações na Web no TechNet em [Uninstall-ADServiceAccount](https://technet.microsoft.com/library/ee617202.aspx).



## <a name="BKMK_Links"></a>Consulte também

-   [Visão geral de contas de serviço gerenciado de grupo](group-managed-service-accounts-overview.md)
