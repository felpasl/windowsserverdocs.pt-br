---
title: Usando o comando New-MulticastTransmission
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c1f1dc46-dd50-4eb9-9f72-cf0e5d71bd3d
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 8a6893d34e8f1242966d644159823277cf71a0c0
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71401989"
---
# <a name="using-the-new-multicasttransmission-command"></a>Usando o comando New-MulticastTransmission

>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Cria uma nova transmissão multicast para uma imagem. Esse comando é equivalente a criar uma transmissão usando o snap-in do MMC dos serviços de implantação do Windows (clique com o botão direito do mouse no nó **transmissões multicast** e clique em **criar transmissão multicast**). Você deve usar esse comando quando tiver o serviço de função servidor de implantação e o serviço de função de servidor de transporte instalados (que é a instalação padrão). Se você tiver apenas o serviço de função de servidor de transporte instalado, use [usando o comando New-namespace](using-the-new-namespace-command.md).
## <a name="syntax"></a>Sintaxe
para transmissões de imagens de instalação:
```
wdsutil [Options] /New-MulticastTransmissiomedia:<Image name>
        [/Server:<Server name>]
        /FriendlyName:<Friendly name>
        [/Description:<Description>]
        /Transmissiontype: {AutoCast | ScheduledCast}
            [/time:<YYYY/MM/DD:hh:mm>]
            [/Clients:<Num of Clients>]
      mediatype:Install
       mediaGroup:<Image Group>]
        [/Filename:<File name>]
```
para transmissões de imagem de inicialização (com suporte apenas para o Windows Server 2008 R2):
```
wdsutil [Options] /New-MulticastTransmissiomedia:<Image name>
        [/Server:<Server name>]
        /FriendlyName:<Friendly name>
        [/Description:<Description>]
        /Transmissiontype: {AutoCast | ScheduledCast}
            [/time:<YYYY/MM/DD:hh:mm>]
            [/Clients:<Num of Clients>]
      mediatype:Boot
        /Architecture:{x86 | ia64 | x64}
        [/Filename:<File name>]
```
## <a name="parameters"></a>Parâmetros
|Parâmetro|Descrição|
|-------|--------|
mídia: <Image name>|Especifica o nome da imagem a ser transmitida usando multicast.|
|[/Server:<Server name>]|Especifica o nome do servidor. Esse pode ser o nome NetBIOS ou o FQDN (nome de domínio totalmente qualificado). Se nenhum nome de servidor for especificado, o servidor local será usado.|
|/FriendlyName: <Friendly name>|Especifica o nome amigável da transmissão.|
|[/Description:<Description>]|Especifica a descrição da transmissão.|
MediaType: {instalação&#124;de inicialização}|Especifica o tipo de imagem a ser transmitida usando multicast. Observação só há suporte para a **inicialização** no Windows Server 2008 R2.|
|\mediaGroup: <Image group name>]|Especifica o grupo de imagens que contém a imagem. Se nenhum nome de grupo de imagens for especificado e houver apenas um grupo de imagens no servidor, esse grupo de imagens será usado. Se houver mais de um grupo de imagens no servidor, você deverá usar essa opção para especificar o nome do grupo de imagens.|
|[/Filename:<File name>]|Especifica o nome do arquivo. Se a imagem de origem não puder ser identificada exclusivamente pelo nome, você deverá usar essa opção para especificar o nome do arquivo.|
|/TransmissionType: {AutoCast &#124; ScheduledCast}|Especifica se a transmissão deve ser iniciada automaticamente (AutoCast) ou com base nos critérios de início especificados (ScheduledCast).<br /><br /><ul><li>**Conversão automática**. Esse tipo de transmissão indica que assim que um cliente aplicável solicitar uma imagem de instalação, uma transmissão multicast da imagem selecionada será iniciada. À medida que outros clientes solicitam a mesma imagem, eles são adicionados à transmissão que já foi iniciada.</li><li>**Com conversão agendada**. Esse tipo de transmissão define os critérios de início para a transmissão com base no número de clientes que estão solicitando uma imagem e/ou um dia e hora específicos. Você pode especificar as seguintes opções:<br /><br /><ul><li>[/time: <time>] – define a hora em que a transmissão deve começar usando o seguinte formato: AAAA/MM/DD: hh: mm.</li><li>[/Clients: <Number of clients>]-define o número mínimo de clientes a aguardar antes de iniciar a transmissão.</li></ul></li></ul>|
|/Architecture: {x86 &#124; IA64 &#124; x64}|Especifica a arquitetura da imagem de inicialização a ser transmitida usando multicast. Como é possível ter o mesmo nome para imagens de inicialização de diferentes arquiteturas, você deve especificar a arquitetura para garantir que a imagem correta seja usada.|
|[/Filename:<File name>]|Especifica o nome do arquivo. Se a imagem de origem não puder ser identificada exclusivamente pelo nome, você deverá especificar o nome do arquivo.|
## <a name="BKMK_examples"></a>Disso
Para criar uma transmissão de conversão automática de uma imagem de inicialização no Windows Server 2008 R2, digite:
```
wdsutil /New-MulticastTransmission /FriendlyName:"WDS Boot Transmission"
/Image:"X64 Boot Imagemediatype:Boot /Architecture:x64 /Transmissiontype:AutoCast
```
Para criar uma transmissão de conversão automática de uma imagem de instalação, digite:
```
wdsutil /New-MulticastTransmission /FriendlyName:"WDS AutoCast Transmission"
/Image:"Vista with Officemediatype:Install /Transmissiontype:AutoCast
```
Para criar uma transmissão de conversão agendada de uma imagem de instalação, digite:
```
wdsutil /New-MulticastTransmission /FriendlyName:"WDS SchedCast Transmission" /Server:MyWDSServemedia:"Vista with Officemediatype:Install 
/Transmissiontype:ScheduledCast /time:"2006/11/20:17:00" /Clients:100
```
#### <a name="additional-references"></a>Referências adicionais
[Chave de sintaxe de linha de comando](command-line-syntax-key.md)
[usando o comando get-AllMulticastTransmissions](using-the-get-allmulticasttransmissions-command.md)
[usando o comando Get-MulticastTransmission](using-the-get-multicasttransmission-command.md)
[usando o comando Remove-MulticastTransmission](using-the-remove-multicasttransmission-command.md)
[ Subcomando: Start-MulticastTransmission](subcommand-start-multicasttransmission.md)
