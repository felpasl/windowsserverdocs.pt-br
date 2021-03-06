---
title: Gerenciar Acesso Remoto
description: Este tópico fornece informações sobre como gerenciar o acesso remoto no Windows Server 2016.
manager: brianlic
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: networking-ras
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1459819a-b1b6-4800-8770-4a85d02c7a2b
ms.author: pashort
author: shortpatti
ms.openlocfilehash: 2b9065b2d4541063c8cd6f09d47f48a9ba7833e1
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71404659"
---
# <a name="manage-remote-access"></a>Gerenciar Acesso Remoto

>Aplica-se a: Windows Server (Canal Semestral), Windows Server 2016

O cenário de implantação do gerenciamento de cliente remoto do DirectAccess usa o DirectAccess para manter os clientes pela Internet. Esta seção explica o cenário, incluindo suas fases, funções, recursos e links para recursos adicionais.  
  
O Windows Server 2016 e o Windows Server 2012 combinam o DirectAccess e o serviço de roteamento e acesso remoto (RRAS) para uma única função de acesso remoto.   
  
> [!NOTE]  
> Além deste tópico, estão disponíveis os seguintes tópicos de gerenciamento de acesso remoto.  
>   
> -   [Usar o monitoramento e contabilização do acesso remoto](monitoring-and-accounting/Use-Remote-Access-Monitoring-and-Accounting.md)  
> -   [Gerenciar clientes do DirectAccess remotamente](manage-remote-clients/Manage-DirectAccess-Clients-Remotely.md)  
  
## <a name="BKMK_OVER"></a>Descrição do cenário  
Os computadores cliente DirectAccess estão conectados à intranet sempre que estiverem conectados à Internet, independentemente de se o usuário efetuou logon no computador. Eles podem ser gerenciados como recursos de intranet e mantidos atualizados com alterações à Política de Grupo, atualizações do sistema operacional, atualizações de antimalware e outras alterações organizacionais.  
  
Em alguns casos, os computadores ou servidores da intranet devem iniciar as conexões com os clientes DirectAccess. Por exemplo, os técnicos de ajuda podem usar conexões de área de trabalho remota para conectar-se e solucionar problemas de clientes remotos do DirectAccess. Este cenário permite que você mantenha sua solução de acesso remoto existente em vigor para a conectividade do usuário, ao mesmo tempo utilizando o DirectAccess para gerenciamento remoto.  
  
O DirectAccess fornece uma configuração que dá suporte ao gerenciamento remoto de clientes DirectAccess. Você pode usar uma opção do assistente de implantação que limite a criação de políticas apenas àquelas necessárias para o gerenciamento remoto de computadores cliente.  
  
> [!NOTE]  
> Nessa implantação, não estão disponíveis as opções de configuração de nível de usuário, como criação forçada de túneis, integração da NAP (Proteção de Acesso à Rede) e autenticação de dois fatores.  
  
## <a name="in-this-scenario"></a>Neste cenário  
O cenário de implantação do Gerenciamento de Cliente Remoto do DirectAccess inclui as seguintes etapas para planejamento e configuração.  
  
### <a name="plan-the-deployment"></a>Planejar a implantação  
Há apenas alguns computadores e requisitos de rede para planejar esse cenário. Elas incluem:  
  
-   **Topologia de rede e servidor**: Com o DirectAccess, você pode colocar seu servidor de acesso remoto na borda de sua intranet ou atrás de um firewall ou dispositivo NAT (conversão de endereços de rede).  
  
-   **Servidor de local de rede do DirectAccess**: O servidor de local de rede é usado por clientes DirectAccess para determinar se estão localizados na rede interna. O servidor de local de rede pode ser instalado no servidor do DirectAccess ou em outro servidor.  
  
-   **Clientes DirectAccess**: Decida quais computadores gerenciados serão configurados como clientes do DirectAccess.  
  
### <a name="configure-the-deployment"></a>Configurar a implantação  
Configurar a implantação consiste em várias etapas. Elas incluem:  
  
1.  **Configurar a infraestrutura**: Configure as definições de DNS, adicione o servidor e os computadores cliente a um domínio, se necessário, e configure os grupos de segurança do Active Directory.  
  
    Nesse cenário de implantação, os GPOs (Objetos de Política de Grupo) são criados automaticamente pelo acesso remoto. Para opções de GPO de certificado avançado, consulte [implantando o acesso remoto avançado](assetId:///3475e527-541f-4a34-b940-18d481ac59f6).  
  
2.  **Configurar o servidor de acesso remoto e as configurações de rede**: Configure adaptadores de rede, endereços IP e roteamento.  
  
3.  **Definir as configurações do certificado**: Nesse cenário de implantação, o assistente de Introdução cria certificados autoassinados, portanto, não é necessário configurar a infraestrutura de certificado mais avançada.  
  
4.  **Configurar o servidor de local de rede**:  Neste cenário, o servidor de local de rede será instalado no servidor de acesso remoto.  
  
5.  **Panejar servidores de gerenciamento do DirectAccess**: Os administradores podem gerenciar remotamente os computadores cliente do DirectAccess localizados fora da rede corporativa via Internet. Servidores de gerenciamento incluem computadores usados durante o gerenciamento de cliente remoto (como servidores de atualização).  
  
6.  **Configurar o servidor de Acesso Remoto**: Instale a função de acesso remoto e execute o Assistente para Introdução do DirectAccess para configurar o DirectAccess.  
  
7.  **Verificar a implantação**: Teste um cliente para garantir que ele consiga se conectar à rede interna e a Internet usando o DirectAccess.  
  
## <a name="BKMK_APP"></a>Aplicativos práticos  
Implantar um servidor de Acesso Remoto único para gerenciar clientes DirectAccess fornece:  
  
-   **Facilidade de acesso**: Os computadores cliente gerenciados que executam o Windows 8 ou o Windows 7 podem ser configurados como computadores cliente do DirectAccess. Eles podem acessar os recursos da rede interna por meio do DirectAccess sempre que estiverem conectados à Internet, sem necessidade de entrar em uma conexão VPN. Computadores cliente que não executam um desses sistemas operacionais podem se conectar à rede interna via VPN. O DirectAccess e a VPN são gerenciados no mesmo console e com o mesmo conjunto de assistentes.  
  
-   **Facilidade de gerenciamento**: Computadores cliente DirectAccess conectados à Internet podem ser gerenciados remotamente por administradores de acesso remoto usando o DirectAccess, mesmo quando os computadores cliente não estão localizados na rede corporativa interna. Os computadores cliente que não atendem aos requisitos corporativos podem ser corrigidos automaticamente por servidores de gerenciamento. Um ou mais servidores de Acesso Remoto podem ser gerenciados a partir de um único console de Gerenciamento de Acesso Remoto.  
  
## <a name="BKMK_NEW"></a>Funções e recursos incluídos neste cenário  
A tabela a seguir lista funções e recursos necessários para o cenário:  
  
|Função ou recurso|Como este cenário tem suporte|  
|----------|-----------------|  
|*Função de acesso remoto*|Essa função é instalada e desinstalada usando o console de Gerenciador do Servidor ou o Windows PowerShell. Essa função engloba o DirectAccess, que era anteriormente um recurso no Windows Server 2008 R2 e os Serviços de Roteamento e Acesso Remoto que eram anteriormente um serviço de função na função de servidor NPAS (Serviços de Acesso e Política de Rede). A função Acesso Remoto consiste em dois componentes:<br /><br />1.  VPN do DirectAccess e RRAS (Serviços de Roteamento e Acesso Remoto): DirectAccess e VPN são gerenciados no console de gerenciamento de acesso remoto.<br />2.  RRAS: Os recursos são gerenciados no console de roteamento e acesso remoto.<br /><br />A função de servidor de acesso remoto depende dos seguintes recursos:<br /><br />-Servidor Web (IIS): Necessário para configurar o servidor de local de rede e a investigação Web padrão.<br />-Banco de dados interno do Windows: Usado para contabilidade local no servidor de Acesso Remoto.|  
|Recurso Ferramentas de Gerenciamento de Acesso Remoto|Este recurso é instalado da seguinte maneira:<br /><br />-Por padrão, em um servidor de acesso remoto quando a função de acesso remoto está instalada e dá suporte à interface do usuário do console de gerenciamento remoto.<br />-Como uma opção em um servidor que não está executando a função de servidor de acesso remoto. Nesse caso, é usado para o gerenciamento remoto de um servidor de acesso remoto.<br /><br />Esse recurso consiste no seguinte:<br /><br />-GUI de acesso remoto e ferramentas de linha de comando<br />-Módulo de acesso remoto para Windows PowerShell<br /><br />As dependências incluem:<br /><br />-Console de Gerenciamento de Política de Grupo<br />-Kit de administração do Gerenciador de conexões RAS (CMAK)<br />-Windows PowerShell 3,0<br />-Infraestrutura e ferramentas de gerenciamento gráfico|  
  
## <a name="BKMK_HARD"></a>Requisitos de hardware  
Os requisitos de hardware para este cenário incluem o seguinte:  
  
### <a name="server-requirements"></a>Requisitos de servidor  
  
-   Um computador que atenda aos requisitos de hardware do Windows Server 2016. Para obter mais informações, consulte requisitos de [sistema](https://technet.microsoft.com/windows-server-docs/get-started/system-requirements-and-installation)do Windows Server 2016.  
  
-   O servidor deve ter pelo menos um adaptador de rede instalado e habilitado. Deve haver apenas um adaptador conectado à rede interna corporativa e apenas um conectado à rede externa (Internet).  
  
-   Se for necessário Teredo como um protocolo de transição de IPv6 para IPv4, o adaptador externo do servidor exigirá dois endereços IPv4 públicos consecutivos. Se um único adaptador de rede estiver disponível, apenas IP-HTTPS poderá ser usado como protocolo de transição.  
  
-   Pelo menos um controlador de domínio. Os servidores de Acesso Remoto e os clientes DirectAccess devem ser membros do domínio.  
  
-   Uma autoridade de certificação é necessária no servidor se você não desejar utilizar certificados autoassinados para IP-HTTPS ou servidor de local de rede, ou se desejar utilizar certificados de cliente para autenticação IPsec do cliente.  
  
### <a name="client-requirements"></a>Requisitos do cliente  
  
-   Um computador cliente deve estar executando o Windows 10 ou Windows 8 ou Windows 7.  
  
### <a name="infrastructure-and-management-server-requirements"></a>Requisitos de servidor de gerenciamento e infraestrutura  
  
-   Durante o gerenciamento remoto de computadores cliente DirectAccess, os clientes iniciam comunicações com servidores de gerenciamento, como controladores de domínio, servidores de configuração do System Center e servidores de HRA (autoridade de registro de integridade). Esses servidores fornecem serviços que incluem atualizações do Windows e de antivírus e conformidade do cliente de NAP (Proteção de Acesso à Rede). Você deve implantar os servidores necessários antes de iniciar a implantação do acesso remoto.  
  
-   É necessário um servidor DNS que executa o Windows Server 2016, o Windows Server 2012 R2, o Windows Server 2012, o Windows Server 2008 R2 ou o Windows Server 2008 com SP2.  
  
## <a name="BKMK_SOFT"></a>Requisitos de software  
Os requisitos de software para este cenário incluem:  
  
### <a name="server-requirements"></a>Requisitos de servidor  
  
-   O servidor de Acesso Remoto deve ser um membro do domínio. O servidor pode ser implantado na borda da rede interna, ou atrás de um firewall de borda ou outro dispositivo.  
  
-   Se o servidor de Acesso Remoto estiver localizado atrás de um firewall de borda ou dispositivo de NAT, o dispositivo deve ser configurado para permitir o tráfego de e para o servidor de Acesso Remoto.  
  
-   Administradores que implantam o servidor de acesso remoto exigem permissões de administrador local no servidor e permissões de usuário de domínio. Além disso, o administrador precisa de permissões para os GPOs utilizados na implantação do DirectAccess. Para aproveitar os recursos que restringem a implantação do DirectAccess a apenas computadores móveis, são necessárias permissões de administrador de domínio no controlador de domínio para criar um filtro WMI.  
  
-   Se o servidor de local de rede não estiver localizado no servidor de Acesso Remoto, será necessário um servidor isolado para executá-lo.  
  
### <a name="remote-access-client-requirements"></a>Requisitos de cliente do Acesso Remoto  
  
-   Os clientes do DirectAccess devem ser membros do domínio. Os domínios que contêm clientes podem pertencer à mesma floresta do servidor de Acesso Remoto, ou ter uma relação de confiança bidirecional com a floresta ou o domínio do servidor de Acesso Remoto.  
  
-   Um grupo de segurança do Active Directory é necessário para conter os computadores que serão configurados como clientes do DirectAccess. Computadores não devem ser incluídos em mais de um grupo de segurança que inclua clientes do DirectAccess. Se os clientes forem incluídos em diversos grupos, a resolução do nome dos grupos para solicitações de clientes não funcionará conforme esperado.  
  

