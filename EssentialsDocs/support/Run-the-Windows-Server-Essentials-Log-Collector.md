---
title: Executar o coletor de log do Windows Server Essentials
description: Descreve como usar o Windows Server Essentials
ms.custom: na
ms.date: 10/03/2016
ms.prod: windows-server-2016-essentials
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0d340223-fa24-4c75-ba8e-b654feb120ab
author: nnamuhcs
ms.author: coreyp
manager: dongill
ms.openlocfilehash: 5654f28aeda3c231376ed888a8aa04bc0cf3d000
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66432494"
---
# <a name="run-the-windows-server-essentials-log-collector"></a>Executar o coletor de log do Windows Server Essentials
Você pode executar o coletor de Log do Windows Server Essentials do servidor ou um computador na rede. Se executar o coletor de log do servidor, você só poderá coletar logs do servidor. Se você executar o coletor de log de um computador da rede, você pode optar por coletar logs do servidor, além de logs para esse computador.  
  
 Você deve ter privilégios administrativos apropriados para executar o coletor de log. Se você estiver coletando arquivos de log para um servidor, você deve ser um Administrador de Servidor; se você estiver coletando arquivos de log em um computador de rede, você deve ser um administrador do cliente para esse computador.  
  
#### <a name="to-run-the-log-collector-on-the-server-by-using-the-wizard"></a>Para executar o coletor de log no servidor usando o assistente  
  
1. Sobre o **inicie** página do servidor, clique em **coletor de Log do Windows Server Essentials**.  
  
   > [!NOTE]
   > - Se o programa de coletor de Log não aparecer na **inicie** página, navegue até **%system%\Program arquivos (x86) \Windows Server Essentials Log Collector**e, em seguida, clique duas vezes em **LogCollector** .  
   >   -   Se você não estiver conectado ao servidor com privilégios administrativos, o coletor de log solicitará que você insira suas credenciais.  
  
2. Quando você for solicitado um local salvar os arquivos de log coletados, você pode escolher o local padrão,  **\\ \\< ServerName\>\logs**, ou especificar outro local. Para aceitar o local padrão, clique em **Avançar**. Para alterar o local, clique em **Navegar**, navegue até a pasta onde deseja salvar os arquivos de log e, em seguida, clique em **Salvar**.  
  
   > [!NOTE]
   >  Você não precisará fornecer nomes de arquivo para os arquivos de log. O coletor de Log nomeia a coleção de arquivos zip concatenando o nome do computador e o carimbo de hora do arquivo.  
  
3. Uma barra de progresso é exibida enquanto os logs estão sendo coletados.  
  
4. Para exibir o conteúdo do arquivo de coleta de log, marque a caixa de seleção **Abrir o local do arquivo onde os logs foram salvos** e clique em **Fechar** para fechar o assistente e abrir o arquivo de coleta de log.  
  
#### <a name="to-run-the-log-collector-on-a-network-computer-by-using-the-wizard"></a>Para executar o coletor de log em um computador de rede usando o assistente  
  
1.  Navegue até **%system%\Program arquivos (x86) \Windows Server Essentials Log Collector**e, em seguida, clique duas vezes no arquivo **LogCollector.exe**.  
  
    > [!NOTE]
    >  Se você não estiver conectado ao computador de rede com privilégios administrativos, insira seu nome de usuário e senha quando solicitado e clique em **Avançar**.  
  
2.  Selecione os logs que gostaria de coletar, da seguinte maneira:  
  
    1.  Marque a caixa de seleção **Arquivos de log do servidor** para coletar os arquivos de log no servidor.  
  
    2.  A caixa de seleção **Arquivos de log do computador cliente (este computador)** é marcada por padrão, indicando que o coletor de log coletará os logs do computador de rede que está executando o. Se você deseja coletar logs do servidor, desmarque a caixa de seleção **Arquivos de log do computador cliente (este computador)** .  
  
    3.  Clique em **Avançar**.  
  
3.  Quando solicitado, digite o nome de usuário e a senha de um administrador de servidor e, em seguida, clique em **Avançar**.  
  
4.  Digite ou navegue até o local onde você deseja salvar os arquivos de log e, em seguida, clique em **Avançar**.  
  
    > [!NOTE]
    >  Você não precisará fornecer nomes de arquivo para os arquivos de log. O coletor de Log nomeia a coleção de arquivos zip concatenando o nome do computador e o carimbo de hora do arquivo.  
  
5.  Uma barra de progresso é exibida enquanto os logs estão sendo coletados.  
  
6.  Para exibir o conteúdo do arquivo de coleta de log, marque a caixa de seleção **Abrir o local do arquivo onde os logs foram salvos** e clique em **Fechar** para fechar o assistente e abrir o arquivo de coleta de log.  
  
### <a name="running-the-log-collector-manually"></a>Executando o coletor de log manualmente  
 Depois que o coletor de log for instalado, uma tarefa agendada é criada para executar a ferramenta. Posteriormente, você pode executar o coletor de log do **Gerenciador de tarefas agendadas** sem usar o assistente, caso haja problemas com a inicialização do assistente.  
  
##### <a name="to-manually-run-the-log-collector-on-the-server"></a>Para executar o coletor de log manualmente no servidor  
  
1.  Faça logon diretamente ou remotamente no servidor.  
  
2.  Abra o **Agendador de Tarefas**.  
  
3.  Na raiz da **Biblioteca do Agendador de Tarefas**, navegue até a tarefa agendada denominada **LogCollector**.  
  
4.  Clique com botão direito do mouse em **LogCollector**e clique em **Executar**. O coletor de Log coloca os logs na pasta padrão no servidor,  **\\ \\< ServerName\>\Logs**. Se você não tem permissão de gravação para a pasta ou a pasta não existir, os logs são colocados na **< temp\>**  subdiretório.  
  
##### <a name="to-manually-run-the-log-collector-on-a-network-computer"></a>Para executar o coletor de log manualmente em um computador de rede  
  
1.  Faça logon diretamente ou remotamente no computador de rede.  
  
2.  Abra o **Agendador de Tarefas**.  
  
3.  Na raiz da **Biblioteca do Agendador de Tarefas**, navegue até a tarefa agendada denominada **LogCollector**.  
  
4.  Clique com botão direito do mouse em **LogCollector**e clique em **Executar**. O coletor de Log coloca os logs na **< temp\>**  pasta no computador de rede.
