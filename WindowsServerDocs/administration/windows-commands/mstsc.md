---
title: mstsc
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 59801227-1e7e-4dbd-96e6-f54102a3ce92
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: bf813c75c83154c76d4aeb53a259495d4ad1369e
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71373350"
---
# <a name="mstsc"></a>mstsc

>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Cria conexões com servidores de Host da Sessão da Área de Trabalho Remota (host de Sessão RD) ou outros computadores remotos, edita um arquivo de configuração existente Conexão de Área de Trabalho Remota (. RDP) e migra os arquivos de conexão herdados que foram criados com o Gerenciador de conexões de cliente para novos arquivos de conexão. rdp.
Para obter exemplos de como usar esse comando, consulte [exemplos](#BKMK_examples).
> [!NOTE]
> No Windows Server 2008 R2, os Serviços de Terminal foram renomeados como Serviços de Área de Trabalho Remota. Para descobrir as novidades da versão mais recente, consulte [novidades do serviços de área de trabalho remota no Windows server 2012](https://technet.microsoft.com/library/hh831527) na biblioteca do TechNet do Windows Server.

## <a name="syntax"></a>Sintaxe
```
mstsc.exe [<Connection File>] [/v:<Server>[:<Port>]] [/admin] [/f] [/w:<Width> /h:<Height>] [/public] [/span]
mstsc.exe /edit <Connection File>
mstsc.exe /migrate
```

## <a name="parameters"></a>Parâmetros

|        Parâmetro        |                                                         Descrição                                                         |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------|
|    <Connection File>    |                                   Especifica o nome de um arquivo. rdp para a conexão.                                    |
|   /v: servidor de < [: <Port>]   |                Especifica o computador remoto e, opcionalmente, o número da porta à qual você deseja se conectar.                 |
|         /admin          |                                   Conecta você a uma sessão para administrar o servidor.                                   |
|           /f            |                                    inicia Conexão de Área de Trabalho Remota no modo de tela inteira.                                    |
|       /w: <Width>        |                                      Especifica a largura da janela de Área de Trabalho Remota.                                      |
|       /h: <Height>       |                                     Especifica a altura da janela de Área de Trabalho Remota.                                      |
|         /Public         |                  Executa Área de Trabalho Remota no modo público. No modo público, as senhas e os bitmaps não são armazenados em cache.                  |
|          /span          | Faz a correspondência entre a largura e a altura de Área de Trabalho Remota com a área de trabalho virtual local, abrangendo vários monitores, se necessário. |
| /Edit <Connection File> |                                         Abre o arquivo. rdp especificado para edição.                                          |
|        /migrate         |       Migra os arquivos de conexão herdados que foram criados com o Gerenciador de conexões de cliente para novos arquivos de conexão. rdp.       |
|           /?            |                                            Exibe a ajuda no prompt de comando.                                             |

## <a name="remarks"></a>Comentários
-   Default. rdp é armazenado para cada usuário como um arquivo oculto na pasta documentos do usuário. Os arquivos. rdp criados pelo usuário são salvos por padrão na pasta documentos do usuário, mas podem ser salvos em qualquer lugar.
-   Para abranger os monitores, os monitores devem usar a mesma resolução e devem estar alinhados horizontalmente (ou seja, lado a lado). Atualmente, não há suporte para abranger vários monitores verticalmente no sistema cliente.

## <a name="BKMK_examples"></a>Disso
-   Para se conectar a uma sessão no modo de tela inteira, digite:
    ```
    mstsc /f
    ```
-   Para abrir um arquivo chamado filename. rdp para edição, digite:
    ```
    mstsc /edit filename.rdp
    ```

#### <a name="additional-references"></a>Referências adicionais
-   [Chave da sintaxe de linha de comando](command-line-syntax-key.md)
-   [Serviços de Área de Trabalho Remota &#40;referência de&#41; comando de serviços de terminal](remote-desktop-services-terminal-services-command-reference.md)
