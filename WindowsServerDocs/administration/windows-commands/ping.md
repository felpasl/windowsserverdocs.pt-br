---
title: ping
description: Use ping para verificar a conectividade de rede.
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 49272671-2eec-4fa5-881f-65c24cfbef52
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 07/11/2018
ms.openlocfilehash: 7d9841c12d403d91e14021ff9df65246d322debd
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71372313"
---
# <a name="ping"></a>ping

>Aplicável a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

O comando **ping** verifica a conectividade no nível de IP para outro computador TCP/IP enviando mensagens de solicitação de eco ICMP (Internet Control Message Protocol). O recebimento de mensagens de resposta de eco correspondentes é exibido, juntamente com tempos de ida e volta. ping é o comando TCP/IP primário usado para solucionar problemas de conectividade, acessibilidade e resolução de nomes. Usado sem parâmetros, **ping** exibe a ajuda.

## <a name="syntax"></a>Sintaxe

```
ping [/t] [/a] [/n <Count>] [/l <Size>] [/f] [/I <TTL>] [/v <TOS>] [/r <Count>] [/s <Count>] [{/j <Hostlist> | /k <Hostlist>}] [/w <timeout>] [/R] [/S <Srcaddr>] [/4] [/6] <TargetName>
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|-------|--------|
|/t|Especifica que o ping continua enviando mensagens de solicitação de eco para o destino até que seja interrompido. Para interromper e exibir estatísticas, pressione CTRL + BREAK. Para interromper e encerrar o **ping**, pressione CTRL + C.|
|SRDF|Especifica que a resolução de nome inversa é executada no endereço IP de destino. Se isso for bem-sucedido, o ping exibirá o nome do host correspondente.|
|/n \<contagem\>|Especifica o número de mensagens de solicitação de eco enviadas. O padrão é 4.|
|/l \<tamanho\>|Especifica o comprimento, em bytes, do campo de dados nas mensagens de solicitação de eco enviadas. O padrão é 32. O tamanho máximo é 65.527.|
|/f|Especifica que as mensagens de solicitação de eco são enviadas com o sinalizador não fragmentar no cabeçalho IP definido como 1 (disponível somente em IPv4). A mensagem de solicitação de eco não pode ser fragmentada por roteadores no caminho para o destino. Esse parâmetro é útil para solucionar problemas de PMTU (unidade máxima de transmissão) do caminho.|
|/I \<TTL\>|Especifica o valor do campo TTL no cabeçalho IP para mensagens de solicitação de eco enviadas. O padrão é o valor de TTL padrão para o host. O *TTL* máximo é 255.|
|/v \<TOS\>|Especifica o valor do campo tipo de serviço (TOS) no cabeçalho IP para mensagens de solicitação de eco enviadas (disponível somente em IPv4). O padrão é 0. *Tos* é especificado como um valor decimal de 0 a 255.|
|/r contagem de \<\>|Especifica que a opção de rota de registro no cabeçalho IP é usada para registrar o caminho usado pela mensagem de solicitação de eco e a mensagem de resposta de eco correspondente (disponível somente em IPv4). Cada salto no caminho usa uma entrada na opção de rota de registro. Se possível, especifique uma *contagem* que seja igual ou maior que o número de saltos entre a origem e o destino. A *contagem* deve ser no mínimo 1 e no máximo 9.|
|/s \<contagem\>|Especifica que a opção de carimbo de data/hora da Internet no cabeçalho IP é usada para registrar a hora de chegada da mensagem de solicitação de eco e a mensagem de resposta de eco correspondente para cada salto. A *contagem* deve ser no mínimo 1 e no máximo 4. Isso é necessário para endereços de destino de link local.|
|/j \<hostlist\>|Especifica que as mensagens de solicitação de eco usam a opção de rota de origem flexível no cabeçalho IP com o conjunto de destinos intermediários especificado em *hostlist* (disponível somente em IPv4). Com o roteamento de origem flexível, os destinos intermediários sucessivos podem ser separados por um ou vários roteadores. O número máximo de endereços ou nomes na lista de hosts é 9. A lista de hosts é uma série de endereços IP (em notação decimal pontilhada) separados por espaços.|
|/k \<hostlist\>|Especifica que as mensagens de solicitação de eco usam a opção de rota de origem estrita no cabeçalho IP com o conjunto de destinos intermediários especificado em *hostlist* (disponível somente em IPv4). Com o roteamento de origem estrito, o próximo destino intermediário deve ser diretamente acessível (deve ser um vizinho em uma interface do roteador). O número máximo de endereços ou nomes na lista de hosts é 9. A lista de hosts é uma série de endereços IP (em notação decimal pontilhada) separados por espaços.|
|/w \<tempo limite\>|Especifica a quantidade de tempo, em milissegundos, para aguardar a mensagem de resposta de eco que corresponde a uma determinada mensagem de solicitação de eco a ser recebida. Se a mensagem de resposta de eco não for recebida dentro do tempo limite, a mensagem de erro "tempo limite de solicitação expirado" será exibida. O tempo limite padrão é 4000 (4 segundos).|
|/R|Especifica que o caminho de viagem de ida e volta é rastreado (disponível somente em IPv6).|
|/S \<srcaddr\>|Especifica o endereço de origem a ser usado (disponível somente em IPv6).|
|/4|Especifica que o IPv4 é usado para executar ping. Esse parâmetro não é necessário para identificar o host de destino com um endereço IPv4. Ele só é necessário para identificar o host de destino por nome.|
|/6|Especifica que o IPv6 é usado para executar ping. Esse parâmetro não é necessário para identificar o host de destino com um endereço IPv6. Ele só é necessário para identificar o host de destino por nome.|
|\> de \<TargetName|Especifica o nome do host ou o endereço IP do destino.|
|/?|Exibe a ajuda no prompt de comando.|

## <a name="remarks"></a>Comentários

-   Você pode usar o **ping** para testar o nome do computador e o endereço IP do computador. Se o ping do endereço IP for bem-sucedido, mas o ping do nome do computador não for, você poderá ter um problema de resolução de nome. Nesse caso, verifique se o nome do computador que você está especificando pode ser resolvido por meio do arquivo hosts local, usando consultas DNS (sistema de nomes de domínio) ou por meio de técnicas de resolução de nomes NetBIOS.
-   Esse comando estará disponível somente se o protocolo TCP/IP estiver instalado como um componente nas propriedades de um adaptador de rede em conexões de rede.

## <a name="BKMK_Examples"></a>Disso

O exemplo a seguir mostra a saída do comando **ping** :

```
C:\>ping example.microsoft.com       
         pinging example.microsoft.com [192.168.239.132] with 32 bytes of data:       
         Reply from 192.168.239.132: bytes=32 time=101ms TTL=124       
         Reply from 192.168.239.132: bytes=32 time=100ms TTL=124       
         Reply from 192.168.239.132: bytes=32 time=120ms TTL=124       
         Reply from 192.168.239.132: bytes=32 time=120ms TTL=124
```

Para executar o ping no 10.0.99.221 de destino e resolver 10.0.99.221 para seu nome de host, digite:

```
ping /a 10.0.99.221
```

Para executar ping no 10.0.99.221 de destino com 10 mensagens de solicitação de eco, cada uma delas tem um campo de dados de 1000 bytes, digite:

```
ping /n 10 /l 1000 10.0.99.221
```

Para executar o ping no 10.0.99.221 de destino e registrar a rota para 4 saltos, digite:

```
ping /r 4 10.0.99.221
```

Para executar o ping no 10.0.99.221 de destino e especificar a rota de origem flexível de 10.12.0.1-10.29.3.1-10.1.44.1, digite:

```
ping /j 10.12.0.1 10.29.3.1 10.1.44.1 10.0.99.221
```

## <a name="additional-references"></a>referências adicionais
-   [Chave da sintaxe de linha de comando](command-line-syntax-key.md)
