---
title: Gerenciar a integridade do sistema no Windows Server Essentials
description: Descreve como usar o Windows Server Essentials
ms.custom: na
ms.date: 10/03/2016
ms.prod: windows-server-2016-essentials
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3043f83b-389c-4f37-a1ff-85afe99314fa
author: nnamuhcs
ms.author: coreyp
manager: dongill
ms.openlocfilehash: d9002a1530e114f490ddf1cfb0e5706ddec52431
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66433149"
---
# <a name="manage-system-health-in-windows-server-essentials"></a>Gerenciar a integridade do sistema no Windows Server Essentials

>Aplica-se a: Windows Server 2016 Essentials, Windows Server 2012 R2 Essentials, Windows Server 2012 Essentials
 
 Este tópico aborda como exibir e responder a todos os alertas na rede usando o Painel.  
  
> [!NOTE]
>  No Windows Server Essentials e no Windows Server 2012 R2 com a função experiência Windows Server Essentials instalada, os alertas de integridade para o servidor e os computadores cliente na rede não são mais exibidos no Visualizador de alertas, mas em vez disso, podem ser exibidos sobre o  **Relatórios de integridade** guia do **Home** página.  
  
 Windows Server Essentials monitora ativamente a cada computador que está conectado ao servidor e alerta o administrador problemas relacionados à integridade do sistema, incluindo atualizações essenciais, falta de proteção contra malware, definições de vírus desatualizadas no cliente computadores e outros problemas importantes que exigem ação. Esses problemas são exibidos como alertas no Visualizador de alertas, que pode ser iniciado no painel do servidor ou o Launchpad do computador cliente no Windows Server Essentials, ou sobre o **relatórios de integridade** guia no Windows Server Essentials. Por padrão, os alertas são atualizados a cada trinta minutos, mas você pode avaliar sua rede para alertas a qualquer momento, clicando em **Atualizar** no Visualizador de alertas ou no guia **Relatórios de integridade** .  
  
 Os tópicos a seguir ajudarão você a entender, exibir e responder aos alertas no Visualizador de alerta e também fornece instruções para configurar seu servidor para receber notificações de alerta por email:  
  
-   [Sobre a integridade do relatório de suplemento](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_AddIn)  
  
-   [Exibir alertas usando o Visualizador de alertas](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_View)  
  
-   [Organizar os alertas no Visualizador de alertas](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_Organize)  
  
-   [Responder aos alertas](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_Respond)  
  
-   [Configurar notificações por email para alertas](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_Email)  
  
-   [Alertas potenciais do computador](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_Potential)  
  
##  <a name="BKMK_AddIn"></a> Sobre a integridade do relatório de suplemento  
 O Suplemento de Relatório de integridade para o Windows Server Essentials fornece informações consolidadas sobre a rede do Windows Server Essentials e permite que você distribua essas informações para outras pessoas. Essas informações podem ser exibidas de **relatórios** guia do Painel. Com o **relatórios** guia, você pode fazer o seguinte:  
  
-   [Gerar um relatório sob demanda ou agendamento](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_Generate)  
  
-   [Personalizar o conteúdo do relatório](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_Customize)  
  
-   [O relatório de email](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_emailreport)  
  
> [!NOTE]
>  **Windows Server Essentials:** Você pode baixar o suplemento relatório de integridade do Windows Server Essentials a partir de [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=266342).  
>   
>  **Windows Server Essentials:** Por padrão, o suplemento relatório de integridade é integrado com o Windows Server Essentials ou Windows Server 2012 R2 com a função experiência Windows Server Essentials instalada, e os relatórios de integridade são exibidos na **relatórios de integridade** guia do painel **Home** página.  
  
###  <a name="BKMK_Generate"></a> Gerar um relatório sob demanda ou agendamento  
 Depois de instalar o suplemento de relatório de integridade e reiniciar o Painel, uma nova guia **Relatórios** é adicionada ao Painel geral. Você pode gerar um relatório de integridade sob demanda a qualquer momento clicando na tarefa **Gerar um relatório de integridade** na guia **relatórios** .  
  
 Depois que um relatório de integridade é gerado, um novo item é criado no Painel de lista, identificado por data e hora de geração do relatório. Para abrir um item, você pode clicar duas vezes no painel de lista, ou você pode selecioná-lo e, em seguida, clicar em **abrir o relatório de integridade** no painel de tarefas. O relatório é exibido em uma nova janela no formato HTML.  
  
 Além de gerar um relatório manualmente, você pode gerar o relatório automaticamente sob agendamento por dia ou por hora. Para fazer isso, no painel de tarefas, clique em **Personalizar as configurações do relatório de integridade**e clicar na guia **Agendamento e email** . O recurso **Agendamento** é desativado por padrão e você pode ativá-la selecionando a caixa de seleção **gerar um relatório de integridade no horário agendado** .  
  
###  <a name="BKMK_Customize"></a> Personalizar o conteúdo do relatório  
 O relatório de integridade contém o seguinte:  
  
- **Alertas críticose avisos** Essa opção é consistente com os alertas essenciais e avisos que você vê no Visualizador de alertas no Painel geral. Alertas de informações não são incluídas no relatório de integridade.  
  
- **Erros críticos nos logs de eventos** logs de aplicativos e serviços são verificados e os erros que são registrados em logs nas últimas 24 horas serão apresentados na  seção **Detalhes** do relatório.  
  
- **Backup do servidor** As informações sobre o último backup de servidor são apresentadas na seção **Detalhes** do relatório.  
  
- **Serviços de Início automático não estão funcionandoá em execução** No momento em que o relatório é gerado, se não estiver executando um serviço de início automático, as informações sobre esse serviço serão listadas na seção **Detalhes** do relatório.  
  
- **Atualizações** Você pode ver o status de atualização do servidor e todos os computadores cliente na seção **Detalhes** .  
  
- **Armazenamento** A lista de unidades e sua capacidade é apresentada na seção**Detalhes** .  
  
  No Relatório de Integridade, primeiro exiba o **Resumo**e, para os itens com ícone de erro vermelho ou um ícone de aviso amarelo, clique no link **Detalhes** na mesma linha para exibir os detalhes do item.  
  
  Se você não estiver interessado em alguns dos pontos de discrimidados que são incluídos no relatório por padrão, você pode personalizar o conteúdo do relatório clicando **personalizar as configurações do relatório de integridade** no painel de tarefas e clicando na guia **conteúdo**. Desmarque as caixas de seleção para o conteúdo que você não deseja ver no relatório. Por exemplo, se você tiver seu próprio plano de backup do servidor e não deseja ver avisos sobre backups do servidor, você pode excluir backups de servidor do relatório desmarcando a **backup do servidor** caixa de seleção.  
  
###  <a name="BKMK_emailreport"></a> O relatório de email  
 Fazer logon no painel para ler relatórios é ainda inconveniente para alguns administradores, especialmente se eles têm mais de um servidor para gerenciar. Com o recurso de email ativado, depois que um relatório é gerado, um email será enviado para uma lista de endereços de email especificado com o conteúdo do relatório. O administrador pode facilmente exibir o relatório de qualquer dispositivo ou qualquer aplicativo cliente e certifique-se de que o servidor está sendo executado no melhor estado de funcionamento.  
  
 Na caixa de diálogo **Personalizar as configurações do Relatório de Integridade** após habilitar emails, altere as configurações de SMTP e especifique uma lista de email destinatários, você observará que uma nova tarefa será exibida no painel de tarefas: **Enviar o relatório de integridade por email**. Para obter mais informações sobre configurações do SMTP, consulte [Set up email notifications for alerts](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_Email).  
  
 Você pode selecionar um relatório existente e, em seguida, clique em **Enviar o relatório de integridade por email**. Você também pode gerar um novo relatório e enviá-lo automaticamente para sua caixa de entrada. Se você configurou uma agenda para o relatório, ele será gerado automaticamente e será entregue automaticamente na caixa de entrada após ser gerado diariamente (ou a cada hora), conforme agenda.  
  
##  <a name="BKMK_View"></a> Exibir alertas usando o Visualizador de alertas  
 Esta seção discute como usar o Painel geral ou Barra Inicial para abrir o Visualizador de alertas para exibir o status de integridade de todos os computadores da rede do servidor.  
  
#### <a name="to-open-the-alert-viewer-by-using-the-dashboard"></a>Para abrir o Visualizador de alertas usando o Painel  
  
1.  Abra o Painel.  
  
2.  No painel de navegação, clique em qualquer um dos ícones de alertas exibidos (essencial, aviso ou informacional). Isso abre o Visualizador de alertas.  
  
#### <a name="to-open-the-alert-viewer-from-the-launchpad"></a>Para abrir o Visualizador de alertas a partir da barra inicial  
  
1.  Em um computador que esteja conectado ao servidor, abra a barra inicial. Se solicitado, faça logon na barra inicial com seu nome de usuário e senha.  
  
2.  Clicar em qualquer ícone de alerta exibido (críticos, de aviso e informativos) na parte inferior da barra inicial para abrir o Visualizador de alerta e siga as instruções no painel de detalhes de alerta do Visualizador de eventos para solucionar o alerta.  
  
##  <a name="BKMK_Organize"></a> Organizar os alertas no Visualizador de alertas  
 Você pode organizar os alertas no Visualizador de alertas e exibi-los com base na gravidade (crítico, aviso ou informacional) ou com base no nome do computador.  
  
#### <a name="to-organize-alerts-in-the-alert-viewer"></a>Para organizar os alertas no Visualizador de alertas  
  
1.  Abra o Painel.  
  
2.  No painel de navegação, clicar em qualquer dos ícones alertas exibidos (crítico, aviso ou informacional). Isso abre o Visualizador de alertas.  
  
3.  Expanda a lista suspensa **Organizar** e siga um destes procedimentos:  
  
    1.  Selecione **Filtrar por computador**e clique no nome do computador para o qual você deseja exibir os alertas. Isso mostra os alertas no Visualizador de alertas somente para o computador selecionado.  
  
    2.  Selecione **Filtrar por tipo de alerta**e clique no tipo alerta (crítico, aviso ou informacional) para o qual você deseja exibir os alertas. Isso exibe apenas o tipo de alerta selecionado no Visualizador de alerta.  
  
##  <a name="BKMK_Respond"></a> Responder aos alertas  
 Quando você encontrar um alerta, você poderá optar por fazer o seguinte:  
  
-   [Resolver um alerta](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_Resolve)  
  
-   [Ignorar um alerta](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_3)  
  
-   [Habilitar um alerta](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_5)  
  
-   [Excluir um alerta](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_4)  
  
###  <a name="BKMK_Resolve"></a> Resolver um alerta  
 Siga as instruções de resolução no Visualizador de alerta para resolver o alerta. Depois que um alerta for resolvido, ele ainda será exibido no Visualizador de alerta até que seja atualizada.  
  
###  <a name="BKMK_3"></a> Ignorar um alerta  
 Você pode optar por ignorar um alerta se você preferir responder a ele mais tarde. Quando você ignorar um alerta, ele continua listado no Visualizador de alerta, mas é desabilitado ou esmaecido. Um alerta ignorado não está incluído na avaliação de integridade geral do computador. Para resolver um alerta ignorado, primeiro você precisa habilitar o alerta.  
  
##### <a name="to-ignore-an-alert"></a>Para ignorar um alerta  
  
1. No computador que está conectado ao servidor do Windows Server Essentials, abra a barra inicial.  
  
2. Na barra inicial, clique em algum dos ícones exibidos alertas (críticos, de aviso e informativos). Isso abre o Visualizador de alertas.  
  
3. No Visualizador de alerta, selecione o alerta que você deseja ignorar, e, em seguida, na seção**tarefas**, clique em **ignorar o alerta**.  
  
   Para responder a um alerta desabilitado, você precisará primeiro habilitar o alerta.  
  
###  <a name="BKMK_5"></a> Habilitar um alerta  
 Você pode habilitar um alerta havia ignorado anteriormente. Depois que o alerta estiver habilitado, você pode resolvê-lo ou excluí-la conforme necessário. Um alerta é exibido como desabilitado quando marcado para ser ignorado. Quando você habilita um alerta desabilitado anteriormente, ele se torna ativo e novamente está incluído na avaliação de integridade geral dos computadores.  
  
##### <a name="to-enable-an-alert"></a>Para habilitar um alerta  
  
1.  No computador que está conectado ao servidor, abra a barra inicial.  
  
2.  Na barra inicial, clique em qualquer ícone de alerta exibido (críticos, de aviso e informativos) para abrir o Visualizador de alerta.  
  
3.  No Visualizador de Alertas, clique com o botão direito do mouse no alerta que você deseja habilitar e, em seguida, clique em **Habilitar o alerta**.  
  
###  <a name="BKMK_4"></a> Excluir um alerta  
 Você pode excluir um alerta se você não deseja resolver ou ignorá-lo. Você pode usar o Visualizador de alertas na barra inicial para excluir alertas gerados para o seu computador. Se você excluir um alerta e o servidor detecta o problema novamente no próximo ciclo de avaliação de integridade de rede, ele gera um novo alerta.  
  
##### <a name="to-delete-an-alert"></a>Para excluir um alerta  
  
1.  No computador que está conectado ao servidor, abra a barra inicial.  
  
2.  Na barra inicial, clique em qualquer ícone de alerta exibido (críticos, de aviso e informativos) para abrir o Visualizador de alerta.  
  
3.  No Visualizador de alerta, clique no alerta que você deseja excluir e, em seguida, clique em **excluir o alerta**.  
  
##  <a name="BKMK_Email"></a> Configurar notificações por email para alertas  
 Você pode configurar seu servidor para receber notificações por email sobre a ocorrência de alertas. As notificações de email para esses alertas contêm informações sobre os problemas de rede e suas etapas de resolução, que é idêntico às informações exibidas no Visualizador de alertas. Algumas das avaliações de integridade de rede são feitas por meio de programação.  
  
 Quando você configura o servidor para enviar notificações de alerta por email, uma notificação de email é enviada para alertas encontradas durante a avaliação de integridade da rede. No entanto, nem todos os alertas relatados no Visualizador de alertas são relatados via email.  
  
 A cada 30 minutos, a Tarefa de Avaliação de email de Alerta é executado no servidor, que avalia a rede para alertas. Uma notificação por email é enviada se qualquer alerta, que é definido notificação por email, ocorrer. Um segundo email não é enviado se o alerta ainda estiver ativo no próximo ciclo de avaliação para evitar a saturação da sua caixa de correio. No entanto, se for detectado um novo alerta dentro de um ciclo de avaliação de alerta futuras, uma notificação de email é enviada, e  inclui os alertas novos e anteriores.  
  
###  <a name="BKMK_list"></a> Alertas resultam em notificações por email  
 Os seguintes alertas no Visualizador de alertas resultam em notificações por email quando você configurar seu servidor para enviar notificações por email para alertas:  
  
-   Existem erros em um backup do computador cliente.  
  
-   O servidor foi reiniciado.  
  
-   Um ou mais serviços não estão em execução.  
  
-   O serviço de armazenamento do Windows Server não está sendo executado.  
  
-   Seu período de avaliação expirou.  
  
-   Ative agora.  
  
-   Desligar o servidor de origem.  
  
-   Os resultados da varredura BPA apresentam erros.  
  
-   Os resultados da varredura BPA apresentam avisos.  
  
-   Um certificado não está disponível para o Acesso em qualquer local.  
  
-   O certificado para o Acesso em qualquer lugar expirou.  
  
-   O roteador não está configurado corretamente.  
  
-   O servidor Web não está configurado corretamente.  
  
-   Serviços de área de trabalho remota não estão configurados corretamente.  
  
-   O firewall não está configurado corretamente.  
  
-   O nome de domínio da Internet expirou.  
  
-   O nome de domínio da Internet não pode ser atualizado.  
  
-   Erro de licença: Forest Trust Check.  
  
-   Erro de licença: Verificação do controlador de domínio.  
  
-   Erro de licença: Verificação da função FSMO.  
  
-   Erro de licença: Políticas FSMO obrigatórias.  
  
-   Erro de licença: Políticas de carga obrigatória.  
  
-   Erro de licença: Serviços de domínio Active Directory.  
  
-   Sua assinatura do Office 365 expirou.  
  
-   Autenticação do Office 365 não foi bem-sucedida.  
  
-   A política de senha não está correta.  
  
-   O serviço de sincronização de senha não pode possível sincronizar uma senha de usuário com Office 365.  
  
-   Altere sua senha do Windows.  
  
-   A senha do Office 365 não é o mesmo que a senha do Windows.  
  
-   Não é possível conectar ao Exchange Server.  
  
-   Microsoft Exchange Server tem um problema.  
  
-   Um ou mais discos rígidos no Backup do servidor não estão conectados.  
  
-   O disco rígido de backup não tem espaço livre suficiente para o Backup do servidor.  
  
-   Backup do servidor não foi bem-sucedido porque um percurso instantâneo não pôde ser realizado.  
  
-   Um backup agendado não foi concluído com êxito.  
  
-   Uma ou mais pastas de servidor predefinidos estão ausentes.  
  
-   Espaço livre é baixo em um ou mais discos rígidos de servidor.  
  
-   O gravador VSS do serviço de armazenamento não está em execução.  
  
-   Capacidade de armazenamento baixa em unidades de disco rígido.  
  
-   Uma ou mais unidades não estão funcionando e estão offline.  
  
###  <a name="BKMK_SMTP"></a> Configurando o SMTP no seu servidor para enviar notificações de alerta por email no Windows Server Essentials  
 Esta seção discute como configurar seu servidor para enviar notificações por email para alertas.  
  
> [!NOTE]
>  Você pode baixar o suplemento relatório de integridade do Windows Server Essentials a partir de [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=266342).  
  
##### <a name="to-set-up-email-notification-for-alerts"></a>Para configurar a notificação de email de alerta  
  
1.  No **Painel**, abra o **Visualizador de Alertas**.  
  
2.  No **Visualizador de Alertas**, clique em **Configurar notificação de email de alerta**.  
  
3.  Na janela **Configurar notificação de email de alerta** , clique em **Habilitar**.  
  
4.  No **Configurações de SMTP** janela, faça o seguinte:  
  
    1.  Em **Do endereço de email**, digite o endereço de email que você deseja usar para enviar o email de alertas. Este endereço de email será exibido como o endereço do remetente na notificação de alerta.  
  
    2.  Em **Nome do servidor SMTP**, na caixa de texto **Do endereço de email** , digite o nome do servidor SMTP que você especificou na etapa 4a. (Consulte a tabela 1 para obter uma lista de alguns nomes de servidor SMTP).  
  
    3.  Para **Porta SMTP**, digite o número da porta usada pelo servidor SMTP para enviar e receber email. (Consulte a tabela 1 para os números de porta que são usados por alguns dos servidores SMTP).  
  
    4.  Selecione **Este servidor requer uma conexão segura (SSL)** se o servidor SMTP usa SSL (consulte a tabela 1).  
  
    5.  Selecione **este servidor requer autenticação** se o servidor SMTP pedir um informações de nome e a senha do usuário (consulte a tabela 1). Se você selecionar essa caixa de seleção, digite o nome de usuário e senha do endereço de -email que você inseriu no campo **Do endereço de email** na etapa 4a e clique **OK**.  
  
    > [!NOTE]
    >  Você pode obter as informações sobre o nome do servidor SMTP, o número da porta e o uso SSL do provedor de serviços de Internet.  
  
     **Tabela 1** nomes de servidor de exemplos de SMTP, autenticação e requisitos de criptografia SSL e números de porta  
  
    |Servidor SMTP|SSL necessário|Autenticação necessária|Número da Porta|Nome da Conta/Nome de Logon|  
    |-----------------|------------------|-----------------------------|-----------------|------------------------------|  
    |smtp.gmail.com|Sim|Sim|587|Fornece o endereço de email completo com nome de domínio e senha para autenticação.|  
    |smtp.live.com|Sim|Sim|587|Fornece o endereço de email completo com nome de domínio e senha para autenticação.|  
    |smtp.comcast.net|Sim|Não|587|Fornece o endereço de email completo com nome de domínio e senha para autenticação.|  
    |Yahoo.com|Não|Sim|25|Forneça apenas o endereço de email sem um nome de domínio para o nome de usuário.|  
  
5.  No **configurar notificação de alertas**, para **Destinatários de email**, digite os endereços de email das pessoas que você quer que receba as notificações de alerta por email. Certifique-se de separar cada endereço de email com um ponto e vírgula (;).  
  
6.  Para verificar se você configurou seu servidor SMTP configurações corretamente para enviar notificações de emails de alerta, clique em **aplicar e enviar emails**.  
  
    > [!NOTE]
    >  Quando você clica em **aplicar e enviar emails**, geralmente você receberá uma notificação de email de amostra com alertas de integridade não listados. No entanto, se um alerta de integridade configurado para enviar uma notificação por email for identificado durante esse processo de teste, esse alerta é incluído no email de teste.  
  
### <a name="configuring-smtp-on-your-server-to-send-health-reports-in-windows-server-essentials"></a>Configurando o SMTP no seu servidor para enviar relatórios de integridade no Windows Server Essentials  
 Esta seção descreve como definir as configurações de SMTP para o servidor para que você possa receber relatórios de integridade por email.  
  
> [!NOTE]
>  Por padrão, o suplemento relatório de integridade é integrado com o Windows Server Essentials ou Windows Server 2012 R2 com a função experiência Windows Server Essentials instalada, e os relatórios de integridade são exibidos na **relatórios de integridade** guia do painel **Home** página.  
  
##### <a name="to-set-up-email-notification-for-health-reports"></a>Configurar  emails de notificação para relatórios de integridade  
  
1.  Em **Painel**, clique na guia **relatórios** .  
  
2.  No painel de tarefas **tarefas de relatório de integridade** , clique em **personalizar as configurações do relatório de integridade**.  
  
3.  Na janela **personalizar as configurações do relatório de integridade** , clique em **agendamento e email** .  
  
4.  Na guia **Agendamento e email**, na seção **email**, faça o seguinte:  
  
    1.  Clique em **habilitar**e digite o endereço de email que você deseja usar para enviar os relatórios de integridade. Esse endereço de email será exibido como o endereço do remetente nos relatórios de integridade são enviados por email.  
  
        1.  Para **nome do servidor SMTP**, digite o nome do servidor SMTP. (Consulte a tabela 1 para obter uma lista de alguns nomes de servidor SMTP).  
  
        2.  Para **Porta SMTP**, digite o número da porta usada pelo servidor SMTP para enviar e receber email. (Consulte a tabela 1 para os números de porta que são usados por alguns dos servidores SMTP).  
  
        3.  Selecione **Este servidor requer uma conexão segura (SSL)** se o servidor SMTP usa SSL (consulte a tabela 1).  
  
        4.  Selecione **este servidor requer autenticação** se o servidor SMTP pedir um informações de nome e a senha do usuário (consulte a tabela 1). Se você selecionar essa caixa de seleção, digite o nome de usuário e senha do endereço de -email que você inseriu no campo **Do endereço de email** na etapa 4a e clique **OK**.  
  
            > [!NOTE]
            >  Você pode obter as informações sobre o nome do servidor SMTP, o número da porta e o uso SSL do provedor de serviços de Internet.  
  
            > [!NOTE]
            >  A Microsoft recomenda que você use SSL porque o relatório pode conter o status do servidor que pode ser usado por pessoas mal-intencionadas para detectar vulnerabilidades (por exemplo: ausente windows update). Habilitar o SSL criptografa os dados em trânsito e reduz o risco de exposição a vulnerabilidade do servidor.  
  
5.  Depois de habilitar o email, o link **configurações de SMTP alteração** é exibido. Também uma nova tarefa, **Enviar o relatório de integridade por email**, é exibido nas **tarefas de relatório de integridade**.  
  
     **Tabela 1** nomes de servidor de exemplos de SMTP, autenticação e requisitos de criptografia SSL e números de porta  
  
    |Servidor SMTP|SSL necessário|Autenticação necessária|Número da Porta|Nome da Conta/Nome de Logon|  
    |-----------------|------------------|-----------------------------|-----------------|------------------------------|  
    |smtp.gmail.com|Sim|Sim|587|Fornece o endereço de email completo com nome de domínio e senha para autenticação.|  
    |smtp.live.com|Sim|Sim|587|Fornece o endereço de email completo com nome de domínio e senha para autenticação.|  
    |smtp.comcast.net|Sim|Não|587|Fornece o endereço de email completo com nome de domínio e senha para autenticação.|  
    |Yahoo.com|Não|Sim|25|Forneça apenas o endereço de email sem um nome de domínio para o nome de usuário.|  
  
6.  Em **personalizar as configurações do relatório de integridade**, para **automaticamente enviar o relatório de integridade para os destinatários de email a seguir:** , digite os endereços de email das pessoas que você deseja que recebam os relatórios de integridade por email. Certifique-se de separar cada endereço de email com um ponto e vírgula (;).  
  
7.  Para verificar se você configurou suas configurações do servidor SMTP corretamente para enviar relatórios de integridade através de email, a partir da guia Relatório de integridade no Painel, selecione um relatório, e clique em **Enviar o relatório de integridade por Email** no painel de tarefas.  
  
##  <a name="BKMK_Potential"></a> Alertas potenciais do computador  
 Esta seção discute entender e gerenciar os alertas que são específicos para o computador que esteja conectado ao servidor e que aparecem na barra inicial do computador.  
  
 A tabela a seguir lista alguns dos alertas ao computador que podem ser gerados e exibidos no Visualizador de alertas se elas forem aplicáveis ao seu computador.  
  
|Título do alerta|Impacto e resolução de alerta|  
|-----------------|---------------------------------|  
|O status atual do firewall de rede fornece proteção reduzida para este computador.|Pessoas não autorizadas ou software poderá acessar este computador se o Firewall do Windows não estiver ativado.|  
|Se a Proteção anti-vírus estiver desativada, não instalado ou não atualizado.|Os dados no seu computador estão em risco se a configuração de segurança da **proteção anti-vírus** estiver desativada ou não atualizada. [To protect your computer](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_Protect), siga as etapas indicadas.|  
|Spyware e software de proteção indesejado está desativado, não instalado ou não atualizado.|Os dados no seu computador estão em risco se o **Spyware e o software de proteção anti-vírus** estiver desativado ou não atualizado. [To protect your computer](Manage-System-Health-in-Windows-Server-Essentials.md#BKMK_Protect), siga as etapas indicadas.|  
|O Windows Update está desativado.|Você não poderá se beneficiar com as funcionalidades novas e corrigidas de atualizações, a menos que o Windows Update esteja ativado. Para ativar o Windows Update, no Visualizador de alertas, clique em **abrir o Windows Update**.<br /><br /> Se a tarefa **abrir o Windows Update** não for exibida, você não está conectado ao computador onde o alerta foi gerado. Você deve estar conectado ao computador onde o alerta foi criado para executar essa tarefa no Visualizador de alertas.|  
|Atualizações importantes devem ser instaladas.|Você não poderá se beneficiar com as funcionalidades novas e corrigidas de atualizações, a menos que o Windows Update esteja ativado. Para ativar o Windows Update, no Visualizador de alertas, clique em **abrir o Windows Update**.<br /><br /> Se a tarefa **abrir o Windows Update** não for exibida, você não está conectado ao computador onde o alerta foi gerado. Você deve estar conectado ao computador onde o alerta foi criado para executar essa tarefa no Visualizador de alertas.|  
|Reinicie o computador para aplicar as atualizações.|Você não poderá se beneficiar com as funcionalidades novas e corrigidas das atualizações até que sejam aplicadas. Salvar todos os dados e reiniciar o computador para aplicar as atualizações.|  
|O Espaço livre é baixo em unidades de disco rígido.|Se espaço não for disponibilizado, você não poderá salvar informações adicionais. Para aumentar o espaço livre no computador, considere as seguintes opções:<br /><br /> -Adicione um novo disco rígido.<br /><br /> -Execute **limpeza de disco** para remover arquivos temporários e antigos.<br /><br /> -Mova os arquivos para uma pasta compartilhada em outro computador.<br /><br /> -Arquivar os arquivos em mídia removível, como um CD, DVD ou um disco rígido externo.|  
|O agente **histórico de arquivos** no servidor não está configurado corretamente para funcionar no computador.|Não é possível criar backups do histórico de arquivos.|  
|Um ou mais serviços não estão em execução.||  
|Altere sua senha do Windows.||  
|A senha do Microsoft Office 365 não é a mesma que a senha do Windows.||  
  
###  <a name="BKMK_Protect"></a> Para proteger seu computador  
  
1.  Abrir a Central de segurança.  
  
2.  Determine o status da proteção anti-vírus instalada.  
  
3.  Execute uma das tarefas a seguir, dependendo do status de proteção:  
  
    -   Se não estiver habilitada, habilite.  
  
    -   Se não for atualizado, conclua o processo para atualizar as assinaturas.  
  
    -   Se um anti-vírus não está instalado, considere instalá-lo.  
  
## <a name="see-also"></a>Consulte também  
  
-   [Utilizar o Windows Server Essentials](../use/Use-Windows-Server-Essentials.md)  
  
-   [Gerenciar o Windows Server Essentials](Manage-Windows-Server-Essentials.md)
