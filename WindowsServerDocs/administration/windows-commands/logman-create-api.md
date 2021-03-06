---
title: criar API do logman
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2ecc0a75-2613-464a-8616-c5dc404bb736
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 512602213fcfd95770af0e27b721a589ed489771
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71374601"
---
# <a name="logman-create-api"></a>criar API do logman

>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

criar um coletor de dados de rastreamento de API.  

## <a name="syntax"></a>Sintaxe  
```  
logman create api <[-n] <name>> [options]  
```  
## <a name="parameters"></a>Parâmetros  

|                    Parâmetro                     |                                                                               Descrição                                                                               |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                        /?                        |                                                                    Exibe a ajuda contextual.                                                                     |
|                -s <computer name>                |                                                          Execute o comando no computador remoto especificado.                                                          |
|                 -config <value>                  |                                                         Especifica o arquivo de configurações que contém as opções de comando.                                                         |
|                   [-n] <name>                    |                                                                       Nome do objeto de destino.                                                                        |
| -f < bin&#124;bincirc&#124;CSV&#124;TSV&#124;SQL > |                                                            Especifica o formato de log para o coletor de dados.                                                             |
|             -[-] u < usuário [senha] >              | Especifica o usuário a ser executado como. Inserir um \* para a senha produz uma solicitação para a senha. A senha não é exibida quando você a digita no prompt de senha. |
|    -m < [início] [parar] [[Iniciar] [parar] [...]] >    |                                                Altere para início ou parada manual em vez de uma hora de início ou de término agendada.                                                 |
|                -RF < [[hh:] mm:] SS >                |                                                        Execute o coletor de dados para o período de tempo especificado.                                                         |
|        -b < M/d/AAAA h:mm: SS [AM&#124;PM] >         |                                                              Comece a coletar dados no horário especificado.                                                               |
|        -e < M/d/AAAA h:mm: SS [AM&#124;PM] >         |                                                               Terminar a coleta de dados na hora especificada.                                                                |
|                -si < [[hh:] mm:] SS >                |                                                 Especifica o intervalo de amostragem para coletores de dados de contador de desempenho.                                                  |
|              -o < DSN&#124;de caminho! log >              |                                              Especifica o arquivo de log de saída ou o DSN e o nome do conjunto de logs em um banco de dados SQL.                                               |
|                      -[-] r                       |                                                  Repita o coletor de dados diariamente nas horas de início e término especificadas.                                                  |
|                      -[-] um                       |                                                                     anexar a um arquivo de log existente.                                                                     |
|                      -[-] Omo                      |                                                                     Substituir um arquivo de log existente.                                                                     |
|           -[-] v < nnnnnn&#124;mmddhhmm >           |                                                   Anexe informações de controle de versão do arquivo ao final do nome do arquivo de log.                                                   |
|                  -[-] RC <task>                   |                                                         Execute o comando especificado cada vez que o log for fechado.                                                          |
|                 -[-] máx. <value>                  |                                                 Tamanho máximo do arquivo de log em MB ou número máximo de registros para logs SQL.                                                  |
|              -[-] CNF < [[hh:] mm:] SS >              |     Quando o tempo for especificado, crie um novo arquivo quando o tempo especificado tiver decorrido. Quando a hora não for especificada, crie um novo arquivo quando o tamanho máximo for excedido.     |
|                        -y                        |                                                             Responda sim a todas as perguntas sem avisar.                                                              |
|            -mods < caminho [caminho [...]] >             |                                                          Especifica a lista de módulos da qual registrar chamadas de API.                                                           |
|     -inapis < módulo! API [módulo! API [...]] >      |                                                         Especifica a lista de chamadas de API a serem incluídas no registro em log.                                                          |
|     -exapis < módulo! API [módulo! API [...]] >      |                                                        Especifica a lista de chamadas de API a serem excluídas do registro em log.                                                         |
|                     -[-] ano                      |                                                     Somente nomes de API de log (-ano) ou não registram somente os nomes de API (-ano).                                                     |
|                  -[-] recursivo                   |                                          Registrar (-recursivo) ou não registrar (-recursivo) APIs recursivamente além da primeira camada.                                           |
|                   -exe <value>                   |                                                        Especifica o caminho completo para um executável para rastreamento de API.                                                        |

## <a name="remarks"></a>Comentários  
Onde [-] está listado, um extra-nega a opção.  
## <a name="BKMK_examples"></a>Disso  
O comando a seguir cria um contador de rastreamento de API chamado trace_notepad para o arquivo executável c:\Windows\Notepad.exe e gera os resultados para o arquivo c:\notepad.etl.  
```  
logman create api trace_notepad -exe c:\windows\notepad.exe -o c:\notepad.etl  
```  
O comando a seguir cria um contador de rastreamento de API chamado trace_notepad para o arquivo executável c:\Windows\Notepad.exe coletando valores produzidos pelo módulo c:\windows\system32\advapi32.dll.  
```  
logman create api trace_notepad -exe c:\windows\notepad.exe -mods c:\windows\system32\advapi32.dll  
```  
O comando a seguir cria um contador de rastreamento de API chamado trace_notepad para o arquivo executável c:\Windows\Notepad.exe, excluindo a chamada à API TlsGetValue produzida pelo módulo Kernel32. dll.  
```  
logman create api trace_notepad -exe c:\windows\notepad.exe -exapis kernel32.dll!TlsGetValue  
```  
#### <a name="additional-references"></a>Referências adicionais  
[logman](logman.md)  
