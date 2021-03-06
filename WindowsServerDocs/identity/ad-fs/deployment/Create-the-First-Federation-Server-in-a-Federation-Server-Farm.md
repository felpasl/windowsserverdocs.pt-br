---
ms.assetid: 5e334c4e-75a7-453c-83e8-5ab4243cc685
title: Criar o primeiro servidor de federação em um farm de servidores de federação
description: ''
author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server
ms.technology: identity-adfs
ms.author: billmath
ms.openlocfilehash: 09b577ddcf722c6eac17ea145f29f9583d1cdb00
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71408423"
---
# <a name="create-the-first-federation-server-in-a-federation-server-farm"></a>Criar o primeiro servidor de federação em um farm de servidores de federação

Depois de instalar o Serviço de Federação serviço de função e configurar os certificados necessários em um computador, você estará pronto para configurar o computador para se tornar um servidor de Federação. Você pode usar o procedimento a seguir para configurar o computador para se tornar o primeiro servidor de Federação em um novo farm de servidores de Federação usando o assistente de configuração do servidor de Federação AD FS.  
  
O ato de criar o primeiro servidor de federação em um farm também cria um novo Serviço de Federação e torna esse computador o servidor de federação primário. Isso significa que esse computador será configurado com uma cópia de leitura\/gravação do banco de dados de configuração do AD FS. Todos os outros servidores de Federação neste farm devem replicar todas as alterações feitas no servidor de Federação primário para suas leituras\-apenas cópias do banco de dados de configuração de AD FS que eles armazenam localmente. Para obter mais informações sobre esse processo de replicação, consulte [The Role of the AD FS Configuration Database (A função do banco de dados de configuração do AD FS)](../../ad-fs/technical-reference/The-Role-of-the-AD-FS-Configuration-Database.md).  
  
> [!NOTE]  
> Para o\-de logon\-único da Web federado em \(design de\) SSO, você deve ter pelo menos um servidor de Federação na organização do parceiro de conta e pelo menos um servidor de Federação na organização do parceiro de recurso. Para obter mais informações, consulte [Onde colocar um servidor de federação](https://technet.microsoft.com/library/dd807127.aspx).  
  
O mínimo necessário para concluir esse procedimento é a associação em Admins. do Domínio, ou uma conta de domínio delegada à qual foi atribuído acesso de gravação ao contêiner Dados do Programa no Active Directory.  
  
### <a name="to-create-the-first-federation-server-in-a-federation-server-farm"></a>Para criar o primeiro servidor de federação em um farm de servidores de federação  
  
1.  Há duas maneiras de iniciar o assistente de configuração do servidor de Federação AD FS. Para iniciar o assistente, tome uma das seguintes ações:  
  
    -   Depois que a instalação do serviço de função Serviço de Federação for concluída, abra o\-snap de gerenciamento de AD FS no e clique no link **Assistente de configuração do servidor de federação AD FS** na página **visão geral** ou no painel **ações** .  
  
    -   Sempre que o assistente de instalação for concluído, abra o Windows Explorer, navegue até a pasta **C:\\Windows\\ADFS** e clique duas vezes\-clique em **FsConfigWizard. exe**.  
  
2.  Na página **Bem-vindo**, verifique se **Criar um novo Serviço de Federação** está selecionado e clique em **Avançar**.  
  
3.  Na página **selecionar\-autônomo ou implantação de farm** , clique em **novo farm de servidores de Federação**e clique em **Avançar**.  
  
4.  Na página **Especificar o Nome do Serviço de Federação**, verifique se o **Certificado SSL** que aparece está correto. Se não for o certificado correto, selecione o certificado apropriado na lista **Certificado SSL**.  
  
    Esse certificado é gerado a partir do protocolo SSL \(configurações de\) SSL para o site padrão. Se o Site Padrão tiver somente um certificado SSL configurado, esse certificado será apresentado e automaticamente selecionado para uso. Se vários certificados SSL forem configurados para o Site Padrão, todos esses certificados serão listados aqui e você deverá selecionar um dentre eles. Se não houver configurações do SSL definidas para o Site Padrão, a lista será gerada dos certificados disponíveis no repositório de certificados pessoal no computador local.  
  
    > [!NOTE]  
    > O assistente não permitirá que você substitua o certificado se um certificado SSL estiver configurado para IIS. Isso assegura que qualquer configuração anterior do IIS pretendida para certificados SSL seja preservada. Para resolver essa restrição, você poderá remover o certificado ou reconfigurá-lo manualmente com o Console de Gerenciamento do IIS.  
  
5.  Se o banco de dados de AD FS que você selecionou já existir, a página **banco de dados de configuração AD FS existente detectado** será exibida. Se essa página aparecer, clique em **Excluir banco de dados** e clique em **Avançar**.  
  
    > [!CAUTION]  
    > Selecione esta opção somente quando você tiver certeza de que os dados nesse banco de dado AD FS não são importantes ou que não são usados em um farm de servidores de Federação de produção.  
  
6.  Na página **Especificar uma Conta de Serviço**, clique em **Procurar**. Na caixa de diálogo **Procurar**, localize a conta de domínio que será usada como a conta de serviço nesse novo farm de servidores de federação, e clique em **OK**. Digite uma senha para essa conta, confirme-a e clique em **Avançar**.  
  
    > [!NOTE]  
    > Confira [configurar manualmente uma conta de serviço para um farm de servidores de Federação](Manually-Configure-a-Service-Account-for-a-Federation-Server-Farm.md) para obter mais informações sobre como especificar uma conta de serviço para um farm de servidores de Federação. Cada servidor de Federação no farm de servidores de Federação deve especificar a mesma conta de serviço para o farm estar operacional. Por exemplo, se a conta de serviço criada foi contoso\\ADFS2SVC, cada computador configurado para a função de servidor de Federação e que participará do mesmo farm deverá especificar contoso\\ADFS2SVC nesta etapa no assistente de configuração do servidor de Federação para que o farm esteja operacional.  
  
7.  Na página **Pronto para Aplicar Configurações**, examine os detalhes. Se as configurações parecerem corretas, clique em **Avançar** para começar a configurar AD FS com essas configurações.  
  
8.  Na página **Resultados da Configuração**, examine os resultados. Quando todas as etapas de configuração forem concluídas, clique em **fechar** para sair do assistente.  
  
    > [!IMPORTANT]  
    > Para fins de implantação segura, a resolução de artefato e a detecção de resposta são desabilitadas quando você usa o Assistente de Configuração do Servidor de Federação do AD FS para configurar um farm de servidores de federação. Esse assistente configura automaticamente o Banco de Dados Interno do Windows para armazenar dados de configuração de serviço. No entanto, você pode desfazer essa alteração por engano, habilitando o ponto de extremidade de resolução de artefatos usando o nó **pontos** de extremidade no snap\-de gerenciamento de AD FS no ou o cmdlet Enable\-ADFSEndpoint no Windows PowerShell. Tenha cuidado para não reconfigurar a definição padrão de forma que esse ponto de extremidade permaneça desabilitado ao usar um farm de servidores de federação junto com o Banco de Dados Interno do Windows.  
  
## <a name="additional-references"></a>Referências adicionais  
[Lista de verificação: Configurando um servidor de Federação](Checklist--Setting-Up-a-Federation-Server.md)  
  

