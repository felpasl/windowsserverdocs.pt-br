---
title: Visão geral do Painel no Windows Server Essentials
description: Descreve como usar o Windows Server Essentials
ms.custom: na
ms.date: 10/03/2016
ms.prod: windows-server-2016-essentials
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f70a79de-9c56-4496-89b5-20a1bff2293e
author: nnamuhcs
ms.author: coreyp
manager: dongill
ms.openlocfilehash: 2322fa3f4617e8a8450aaf7fd5ead702574bf759
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66433136"
---
# <a name="overview-of-the-dashboard-in-windows-server-essentials"></a>Visão geral do Painel no Windows Server Essentials

>Aplica-se a: Windows Server 2016 Essentials, Windows Server 2012 R2 Essentials, Windows Server 2012 Essentials
 
 Windows Server Essentials e o Windows Server 2012 R2 Standard com a função Experiência do Windows Server Essentials habilitada incluem um Painel administrativo, que simplifica as tarefas que você pode executar para gerenciar sua rede do Windows Server Essentials e o servidor. Usando o Painel do Windows Server Essentials, você pode:  
  
- Concluir a configuração do servidor  
  
- Acessar e executar tarefas administrativas comuns  
  
- Exibir alertas do servidor e agir sobre eles  
  
- Definir e alterar as configurações do servidor  
  
- Acesso ou procurar tópicos da Ajuda na web  
  
- Acessar recursos da comunidade na web  
  
- Gerenciar contas de usuário  
  
- Gerenciar backups e dispositivos  
  
- Gerenciar configurações de pastas do servidor e unidades de disco rígidos e acesso  
  
- Exibir e gerenciar os aplicativos complementares  
  
- Integrar se com os serviços online da Microsoft  
  
  Este tópico inclui:  
  
- [Recursos básicos do painel](#BKMK_Design)  
  
- [Recursos da página inicial do Dashboard](#BKMK_Home)  
  
- [Seções administrativas do painel](#BKMK_Features)  
  
- [Acessar o painel do Windows Server Essentials](#BKMK_AccessDb)  
  
- [Use o modo de segurança](#BKMK_UseSafeMode)  
  
##  <a name="BKMK_Design"></a> Recursos básicos do painel  
 O Painel do Windows Server Essentials ajuda você a acessar rapidamente os principais recursos de gerenciamento e informações do seu servidor. O painel inclui várias seções. A tabela a seguir descreve as seções.  
  
 
  
|Item|Recurso do Painel|Descrição|  
|----------|-----------------------|-----------------|  
|1|Barra de navegação|Clique em uma seção na barra de navegação para acessar as informações e as tarefas associadas a essa seção. Cada vez que você abrir o painel, a página **Inicial** aparece por padrão.|  
|2|Guias de subseção|As guias da subseção fornecem acesso a uma segunda camada de tarefas administrativas do Windows Server Essentials.|  
|3|Painel de lista|A lista exibe os objetos que você pode gerenciar e inclui informações básicas sobre cada objeto.|  
|4|Painel de detalhes|O painel de detalhes exibe informações adicionais sobre um objeto que você seleciona no modo de exibição de lista.|  
|5|Painel de tarefas|O painel de tarefas contém links para ferramentas e informações que ajudam você a gerenciar as propriedades de um objeto específico (por exemplo, uma conta de usuário ou um computador) ou de configurações globais para a categoria de objeto. O painel de tarefas é dividido nessas duas seções:<br /><br /> **Tarefas do objeto** œ contêm links para informações e ferramentas que ajudam você a gerenciar as propriedades de um objeto que você selecionar na exibição de lista (como uma conta de usuário ou computador).<br /><br /> **Tarefas globais** œ contêm links para informações e ferramentas que ajudam você a gerenciam tarefas globais para uma área de recurso. As tarefas globais incluem tarefas para adicionar novos objetos, definir políticas e assim por diante.|  
|6|Informações e configurações|Esta seção fornece acesso direto para as configurações do servidor e um link de ajuda para obter informações sobre a página do Painel que você está exibindo.|  
|7|Status de alertas|O status de alertas fornece uma indicação visual rápida sobre a integridade do servidor. Clique na imagem de alerta para exibir alertas críticos e importantes.<br /><br /> **Observação:** No Windows Server Essentials e no Windows Server 2012 R2 Standard com a função experiência Windows Server Essentials instalada, o status de alertas está disponível sobre o **informações e configurações** guia.|  
|8|Barra de status|A barra de status exibe o número de objetos que aparecem no modo de exibição de lista. Aplicativos complementares também podem exibir outros status.|  
  
##  <a name="BKMK_Home"></a> Recursos da página inicial do Dashboard  
 Quando você abre o Painel, a página **Inicial** aparece por padrão com a categoria **instalação** exibida. A página **Inicial** do Painel do Windows Server Essentials fornece acesso rápido a tarefas e informações que ajudam você a personalizar o seu servidor e configurar os recursos principais. A página Inicial é composta de quatro áreas funcionais, que expõem as tarefas de configuração e as informações para as opções que você selecionar. A tabela a seguir descreve os recursos.  
  
|Item|Recurso|Descrição|  
|----------|-------------|-----------------|  
|1|Barra de navegação|Clique em uma seção na barra de navegação para acessar as informações e as tarefas associadas a essa seção. Cada vez que você abrir o Painel, a página **Inicial** é exibida por padrão.|  
|2|Painel de categoria|Esse painel exibe as áreas de recursos que fornecem acesso rápido a informações e ferramentas de configuração para ajudarão a configurar e personalizar o servidor. Clique em uma categoria para exibir as tarefas e os recursos que estão associados a essa categoria.|  
|3|Painel de tarefas|Esse painel exibe links para tarefas e informações que se aplicam a uma categoria selecionada. Clique em uma tarefa ou recurso para exibir informações adicionais.|  
|4|Painel de ações|Esse painel fornece uma breve descrição de um recurso ou tarefa e fornece links que abrem assistentes de configuração e as páginas de informações. Clique em um link para tomar novas medidas.|  
  
##  <a name="BKMK_Features"></a> Seções administrativas do painel  
 O Painel do Windows Server Essentials organiza informações de rede e tarefas administrativas em áreas funcionais. A página de gerenciamento para cada área funcional fornece informações sobre os objetos associados a área, por exemplo **Usuários**, ou **Dispositivos**. A página de gerenciamento também inclui as tarefas que você pode usar para exibir ou alterar as configurações ou executar programas que automatizam as tarefas que requerem várias etapas.  
  
 A tabela a seguir descreve as seções administrativas do Painel que estão disponíveis por padrão, após a instalação. A tabela também lista as tarefas que estão disponíveis em cada seção.  
  
|`Section`|Descrição|  
|-------------|-----------------|  
|Início|A página **Inicial** aparece por padrão sempre que você abrir o Painel. Ela inclui tarefas e informações nas seguintes categorias:<br /><br /> **INSTALAÇÃO** œ concluir as tarefas nesta categoria para configurar o servidor pela primeira vez. Para obter informações sobre essas tarefas, consulte [instalar e configurar o Windows Server Essentials](../install/Install-and-Configure-Windows-Server-Essentials.md).<br /><br /> **EMAIL** œ escolha uma opção nesta categoria para integrar um serviço de email com o servidor.<br /><br /> **Observação:** Esta categoria só está disponível no Windows Server Essentials.<br /><br /> **SERVIÇOS** œ escolha uma tarefa nessa categoria para integrar serviços online da Microsoft com o servidor.<br /><br /> **Observação:** Esta categoria só está disponível no Windows Server Essentials e no Windows Server 2012 R2 Standard com a função experiência Windows Server Essentials habilitada.<br /><br /> **ADD-INS** œ clique nessa categoria para instalar complementos importantes para a sua empresa.<br /><br /> **STATUS rápido** œ exibe o status de alto nível do servidor. Clique em um status para exibir as opções de configuração e as informações para o recurso. Se você executar todas as tarefas na categoria instalação, esta categoria é exibida na parte superior do painel de categoria.<br /><br /> **Ajudar a** œ Use a caixa de pesquisa para procurar por ajuda na Web. Clique no link para visitar o site para a opção de suporte selecionado.|  
|Usuários|Para que os usuários acessem os recursos do Windows Server Essentials, você precisará criar contas de usuário usando o Painel do Windows Server Essentials. Depois de criar contas de usuário, você pode gerenciar as contas usando as tarefas que estão disponíveis na página **Usuários** do Painel. Tarefas que você pode executar nessa página incluem:<br /><br /> -Exiba uma lista de contas de usuário.<br /><br /> -Exibir e gerenciar as propriedades de conta de usuário.<br /><br /> -Ativar ou desativar contas de usuário.<br /><br /> -Adicionar ou remover contas de usuário.<br /><br /> -Atribua contas de rede local para contas de serviços online da Microsoft se o servidor estiver integrado com o Office 365.<br /><br /> -Alterar senhas de conta de usuário e gerenciar a política de senha.<br /><br /> Para obter informações sobre como gerenciar contas de usuário, consulte [gerenciar contas de usuário](Manage-User-Accounts-in-Windows-Server-Essentials.md).|  
|Grupos de usuários|**Observação:** Esse recurso está disponível somente no Windows Server Essentials e no Windows Server 2012 R2 Standard com a função experiência Windows Server Essentials habilitada.<br /><br /> Tarefas que você pode executar nessa página incluem:<br /><br /> -Exiba uma lista de grupos de usuários.<br /><br /> -Exibir e gerenciar grupos de usuários.<br /><br /> -Adicionar ou remover grupos de usuários.|  
|Grupos de distribuição|**Observação:** Esse recurso está disponível somente no Windows Server Essentials e no Windows Server 2012 R2 Standard com a função experiência Windows Server Essentials habilitada. Esta guia é exibida apenas quando o Windows Server Essentials é integrado com o Office 365.<br /><br /> Tarefas que você pode executar nessa página incluem:<br /><br /> -Exiba uma lista de grupos de distribuição.<br /><br /> -Adicionar ou remover grupos de distribuição.|  
|Dispositivos|Depois de conectar os computadores na rede do Windows Server Essentials, você pode gerenciá-los da página **Dispositivos** no Painel. Tarefas que você pode executar nessa página incluem:<br /><br /> -Exiba uma lista de computadores que fazem parte de sua rede.<br /><br /> -Gerencie dispositivos móveis, aproveitando a capacidade de gerenciamento de dispositivo móvel do Office 365.<br /><br /> **Observação:** Esse recurso só está disponível no Windows Server Essentials e Windows Server 2012 R2 Standard com a função experiência Windows Server Essentials habilitada.<br /><br /> – Exiba as propriedades de computador e os alertas de integridade de cada computador.<br /><br /> -Configurar e gerenciar backups do computador.<br /><br /> -Restaure arquivos e pastas em computadores.<br /><br /> -Estabelecer uma conexão de área de trabalho remota para um computador<br /><br /> -Personalizar configurações de Backup do computador e histórico de arquivos<br /><br /> Para obter informações sobre como gerenciar computadores e backups, consulte [gerenciar dispositivos](Manage-Devices-in-Windows-Server-Essentials.md).|  
|Armazenamento|Dependendo da versão do Windows Server Essentials em execução, a seção **Armazenamento** do Painel contém seguintes seções por padrão.<br /><br /> -A **pastas do servidor** subseção inclui tarefas que ajudam você a exibir e gerenciar as propriedades de pastas do servidor. A página também inclui tarefas para abrir e adicionar pastas do servidor.<br /><br /> -A **unidades de disco rígido** página inclui tarefas que ajudam você a exibir e verificar a integridade das unidades que estão anexados ao servidor.<br /><br /> -No Windows Server Essentials e Windows Server 2012 R2 Standard com a função de experiência do Windows Server Essentials habilitada, o **bibliotecas do SharePoint** página inclui tarefas que ajudam você a gerenciar as bibliotecas do SharePoint no Office 365 serviço.<br /><br /> Para obter informações sobre como gerenciar pastas do servidor, consulte [Manage Server Folders](Manage-Server-Folders-in-Windows-Server-Essentials.md).<br /><br /> Para obter informações sobre como gerenciar discos rígidos, consulte [Manage Server Storage](Manage-Server-Storage-in-Windows-Server-Essentials.md).|  
|Aplicativos|-A **aplicativos** seção do painel do Windows Server Essentials contém duas subseções por padrão.<br /><br /> Para obter informações sobre como gerenciar aplicativos complementares, consulte [gerenciar aplicativos](Manage-Applications-in-Windows-Server-Essentials.md).<br /><br /> -A **Add-ins** subseção exibe uma lista de complementos instalados e fornece tarefas que permitem que você remover um suplemento e para acessar informações adicionais sobre um suplemento selecionado.<br /><br /> -A **Microsoft Pinpoint** subseção exibe uma lista de aplicativos que estão disponíveis na Microsoft Pinpoint.|  
|Office 365|A guia **Office 365** é exibida apenas quando o Windows Server Essentials está integrado com o Microsoft Office 365. Esta seção contém informações de conta de administrador e de assinatura do Office 365.|  
  
> [!NOTE]
>  Se você instalar um complemento para o Painel do Windows Server Essentials, o complemento pode criar seções administrativas adicionais. Essas seções podem aparecer na barra de navegação principal ou em uma guia subseção.  
  
##  <a name="BKMK_AccessDb"></a> Acessar o painel do Windows Server Essentials  
 Você pode acessar o Painel por meio de um dos seguintes métodos. O método escolhido depende se você está acessando o Painel do servidor, de um computador que está conectado à rede Windows Server Essentials ou de um computador remoto.  
  
 Para ajudar a manter uma rede segura, somente os usuários com permissões administrativas podem acessar o Painel do Windows Server Essentials. Além disso, não é possível usar a conta interna de administrador para entrar no Painel do Windows Server Essentials pela Barra Inicial.  
  
###  <a name="BKMK_Server"></a> Acessar o painel do servidor  
 Quando você instala o Windows Server Essentials, o processo de instalação cria um atalho para o Painel na tela **Iniciar** e também na área de trabalho. Se o atalho está faltando nesses locais, você pode usar o painel de **Pesquisa** para localizar e executar o programa Painel.  
  
##### <a name="to-access-the-dashboard-from-the-server"></a>Para acessar o Painel do servidor  
  
-   Entre no servidor como administrador e siga um destes procedimentos:  
  
    -   Na tela **Iniciar** , clique em **Painel**.  
  
    -   Na área de trabalho, clique duas vezes em **Painel**.  
  
    -   No painel **Pesquisa**, digite **dashboard** e clique em**Painel** nos resultados da pesquisa.  
  
###  <a name="BKMK_Network"></a> Acesse o painel de um computador que está conectado à rede  
 No Windows Server Essentials, depois de ingressar um computador à rede, os administradores podem usar a Barra Inicial para acessar o Painel do computador.  
  
> [!WARNING]
>  No Windows Server Essentials, para se conectar ao painel do computador cliente, clique com botão direito no ícone de bandeja e, em seguida, abra o painel do menu de contexto.  
  
##### <a name="to-access-the-dashboard-by-using-the-launchpad"></a>Para acessar o Painel usando a barra inicial  
  
1.  Em um computador que está associado à rede, abra a **Barra Inicial**.  
  
2.  No menu barra inicial, clique em **Painel**.  
  
3.  Na página **Entrar** do Painel, digite as credenciais de administrador de rede e pressione ENTER.  
  
     Uma conexão remota com o Painel do Windows Server Essentials é aberta.  
  
###  <a name="BKMK_Remote"></a> Acesse o painel de um computador remoto  
 Quando você está trabalhando em um computador remoto, você pode acessar o painel do Windows Server Essentials usando o site de acesso via Web remoto.  
  
##### <a name="to-access-the-dashboard-by-using-remote-web-access"></a>Para acessar o Painel utilizando o Acesso Remoto via Web  
  
1.  No computador remoto, abra um navegador da Internet, como o Internet Explorer.  
  
2.  Na barra de endereços do navegador de Internet, digite o seguinte:**https://<DomainName\>/remota**, onde *DomainName* é o nome de domínio externo de sua organização (por exemplo, contoso.com).  
  
3.  Digite seu nome de usuário e senha para se conectar ao site acesso via Web remoto.  
  
4.  No **computadores** seção o acesso via Web remoto**Home** página, localize seu servidor e clique em **Connect**.  
  
     Uma conexão remota com o Painel é aberta.  
  
    > [!NOTE]
    >  Se o servidor não aparecer na seção **Computadores** da página Inicial, clique em **Conectar mais computadores**, localize o servidor na lista e, em seguida, clique no servidor para se conectar a ele.  
    >   
    >  Para conceder uma permissão de usuário para acessar o painel de acesso remoto via Web, abra a página de propriedades da conta de usuário e, em seguida, selecione a **painel do servidor** opção a **acesso em qualquer lugar** guia.  
  
##  <a name="BKMK_UseSafeMode"></a> Use o modo de segurança  
 O recurso de modo de segurança do Windows Server Essentials monitora os suplementos instalados no servidor. Se o Painel tornar-se instável ou não responder, o modo de segurança detectará e isolará complementos que possam estar causando o problema e os exibirá na página **Configurações do modo seguro** na próxima vez em que você abrir o Painel. Na página **Configurações do modo seguro** , você pode desabilitar e habilitar complementos um a um para determinar qual complemento está causando o problema. Você pode optar por deixar o complemento desabilitado para inicializações futuras, ou você pode desinstalar o complemento.  
  
 É possível exibir uma lista de todos os complementos instalados no servidor a qualquer momento. Você também pode abrir o painel no modo de segurança, que desabilita automaticamente todos os suplementos não-Microsoft. O Windows Server Essentials também permite que você acesse o Painel no modo de segurança de outro computador na rede.  
  
#### <a name="to-view-a-list-of-installed-add-ins"></a>Para exibir uma lista de complementos instalados  
  
-   No D, clique em **Ajuda**e, em seguida, clique em **Configurações do modo de segurança**.  
  
#### <a name="to-open-the-dashboard-in-safe-mode"></a>Para abrir o Painel no modo de segurança  
  
-   No painel **Pesquisa** , digite **safe**e, em seguida, clique em **Painel (Modo de segurança)** nos resultados da pesquisa.  
  
#### <a name="to-open-the-dashboard-in-safe-mode-from-another-computer-on-the-network"></a>Para abrir o Painel no modo de segurança de outro computador na rede  
  
1.  Em um computador que está conectado à rede, abra a Barra Inicial do Windows Server Essentials e clique em **Painel**.  
  
2.  Na página de entrada no Painel, digite o nome de usuário e a senha de uma conta que tenha permissão para entrar no servidor, selecione a caixa de seleção **Permitir que eu selecione os complementos para carregar** e, em seguida, clique na seta para entrar.  
  
## <a name="see-also"></a>Consulte também  
  
-   [Gerenciar aplicativos](Manage-Applications-in-Windows-Server-Essentials.md)  
  
-   [Gerenciar o Windows Server Essentials](Manage-Windows-Server-Essentials.md)