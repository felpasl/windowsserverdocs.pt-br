---
title: netstat
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 60e2718f-93cc-4ceb-bf0e-58a6a6e4fc8b
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 54bd21b7e96275d329e45e825971d9236488c793
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71373256"
---
# <a name="netstat"></a>netstat

>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Exibe conexões TCP ativas, portas nas quais o computador está escutando, estatísticas de Ethernet, a tabela de roteamento de IP, estatísticas de IPv4 (para os protocolos IP, ICMP, TCP e UDP) e estatísticas de IPv6 (para os protocolos IPv6, ICMPv6, TCP sobre IPv6 e UDP sobre IPv6). Usado sem parâmetros, **netstat** EXIBE conexões TCP ativas. 

## <a name="syntax"></a>Sintaxe
```
netstat [-a] [-e] [-n] [-o] [-p <Protocol>] [-r] [-s] [<Interval>]
```

### <a name="parameters"></a>Parâmetros

|   Parâmetro   |                                                                                                                                              Descrição                                                                                                                                              |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      -a       |                                                                                                   Exibe todas as conexões TCP ativas e as portas TCP e UDP nas quais o computador está escutando.                                                                                                   |
|      -e       |                                                                                 Exibe estatísticas de Ethernet, como o número de bytes e de pacotes enviados e recebidos. Esse parâmetro pode ser combinado com **-s**.                                                                                  |
|      -n       |                                                                               Exibe conexões TCP ativas, no entanto, endereços e números de porta são expressos numericamente e nenhuma tentativa é feita para determinar nomes.                                                                               |
|      -o       |                          Exibe conexões TCP ativas e inclui a ID do processo (PID) para cada conexão. Você pode encontrar o aplicativo com base na PID na guia processos no Gerenciador de tarefas do Windows. Esse parâmetro pode ser combinado com **-a**, **-n**e **-p**.                           |
| -p <Protocol> |               Mostra conexões para o protocolo especificado pelo *protocolo*. Nesse caso, o *protocolo* pode ser TCP, UDP, TCPv6 ou UDPv6. Se esse parâmetro for usado com **-s** para exibir estatísticas por protocolo, o *protocolo* poderá ser TCP, UDP, ICMP, IP, TCPv6, UDPv6, ICMPv6 ou IPv6.                |
|      -s       | Exibe estatísticas por protocolo. Por padrão, as estatísticas são mostradas para os protocolos TCP, UDP, ICMP e IP. Se o protocolo IPv6 estiver instalado, as estatísticas serão mostradas para os protocolos TCP sobre IPv6, UDP sobre IPv6, ICMPv6 e IPv6. O parâmetro **-p** pode ser usado para especificar um conjunto de protocolos. |
|      -r       |                                                                                                     Exibe o conteúdo da tabela de roteamento de IP. Isso é equivalente ao comando Route Print.                                                                                                     |
|  <Interval>   |                                                        Exibe novamente as informações selecionadas a cada *intervalo* em segundos. Pressione CTRL + C para parar a reexibição. Se esse parâmetro for omitido, o **netstat** imprime as informações selecionadas apenas uma vez.                                                         |
|      /?       |                                                                                                                                 Exibe a ajuda no prompt de comando.                                                                                                                                  |

## <a name="remarks"></a>Comentários
-   Os parâmetros usados com esse comando devem ser prefixados com um hífen ( **-** ) em vez de uma barra ( **/** ).
-   o **netstat** fornece estatísticas para o seguinte:
    -   Proto o nome do protocolo (TCP ou UDP).
    -   Endereço local o endereço IP do computador local e o número da porta que está sendo usado. O nome do computador local que corresponde ao endereço IP e o nome da porta é mostrado, a menos que o parâmetro **-n** seja especificado. Se a porta ainda não tiver sido estabelecida, o número da porta será mostrado como um asterisco (*).
    -   Endereço externo o endereço IP e o número da porta do computador remoto ao qual o soquete está conectado. Os nomes que correspondem ao endereço IP e à porta são mostrados, a menos que o parâmetro **-n** seja especificado. Se a porta ainda não tiver sido estabelecida, o número da porta será mostrado como um asterisco (*).
    -   status Indica o estado de uma conexão TCP. Os possíveis Estados são os seguintes: CLOSE_WAIT CLOSEDed FIN_WAIT_1 FIN_WAIT_2 LAST_ACK listEN SYN_RECEIVED SYN_SEND timeD_WAIT para obter mais informações sobre os Estados de uma conexão TCP, consulte RFC 793.
-   Esse comando estará disponível somente se o protocolo TCP/IP estiver instalado como um componente nas propriedades de um adaptador de rede em conexões de rede.

## <a name="BKMK_Examples"></a>Disso
Para exibir as estatísticas de Ethernet e as estatísticas de todos os protocolos, digite:
```
netstat -e -s
```
Para exibir as estatísticas somente para os protocolos TCP e UDP, digite:
```
netstat -s -p tcp udp
```
Para exibir conexões TCP ativas e as IDs de processo a cada 5 segundos, digite:
```
netstat -o 5
```
Para exibir conexões TCP ativas e as IDs de processo usando formulário numérico, digite:
```
netstat -n -o
```

## <a name="additional-references"></a>Referências adicionais
-   [Chave da sintaxe de linha de comando](command-line-syntax-key.md)
