---
title: Usando o comando Add-Image
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d5b6f4da-90ba-4b0e-9423-66c8ef5172e2
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: b0d671dd482710c486a6936cdbe3b1cc6b331866
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71363740"
---
# <a name="using-the-add-image-command"></a>Usando o comando Add-Image

>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Adiciona imagens a um servidor dos serviços de implantação do Windows. para obter exemplos de como você pode usar esse comando, consulte [exemplos](#BKMK_examples).
## <a name="syntax"></a>Sintaxe
para imagens de inicialização, use a seguinte sintaxe:
```
wdsutil /add-ImagmediaFile:<wim file path> [/Server:<Server name>mediatype:Boot [/Skipverify] [/Name:<Image name>] [/Description:<Image description>] 
[/Filename:<New wim file name>]
```
para imagens de instalação, use a seguinte sintaxe:
```
wdsutil /add-ImagmediaFile:<wim file path>
     [/Server:<Server name>]
   mediatype:Install
     [/Skipverify]
    mediaGroup:<Image group name>]
     [/SingleImage:<Single image name>]
         [/Name:<Name>]
         [/Description:<Description>]
     [/Filename:<File name>]
     [/UnattendFile:<Unattend file path>]
```
## <a name="parameters"></a>Parâmetros
|Parâmetro|Descrição|
|-------|--------|
mediafile: caminho do arquivo <. wim >|Especifica o caminho completo e o nome de arquivo do arquivo de imagem do Windows (. wim) que contém as imagens a serem adicionadas.|
|[/Server:<Server name>]|Especifica o nome do servidor. Pode ser o nome NetBIOS ou o FQDN (nome de domínio totalmente qualificado). Se um nome do servidor não for especificado, o servidor local será usado.|
MediaType: {instalação&#124;de inicialização}|Especifica o tipo de imagens a serem adicionadas.|
|[/Skipverify]|Especifica que a verificação de integridade não será executada no arquivo de imagem de origem antes que a imagem seja adicionada.|
|[/Name: <Name>]|Define o nome de exibição da imagem.|
|[/Description:<Description>]|Define a descrição da imagem.|
|[/Filename:<Filename>]|Especifica o novo nome de arquivo para o arquivo. wim. Isso permite que você altere o nome do arquivo. wim ao adicionar a imagem. Se nenhum nome de arquivo for especificado, o nome do arquivo de imagem de origem será usado. Em todos os casos, os serviços de implantação do Windows verificam se o nome do arquivo é exclusivo no repositório de imagens de inicialização do computador de destino.|
|\mediaGroup: <Image group name>]|Especifica o nome do grupo de imagens no qual as imagens devem ser adicionadas. Se houver mais de um grupo de imagens no servidor, o grupo de imagens deverá ser especificado. Se isso não for especificado e um grupo de imagens ainda não existir, um novo grupo de imagens será criado. Caso contrário, o grupo de imagens existente será usado.|
|[/SingleImage: <Single image name>] [/Name: <Name>] [/Description:<Description>]|Copia a imagem única especificada de um arquivo. wim e define o nome de exibição e a descrição da imagem.|
|[/UnattendFile:<Unattend file path>]|Especifica o caminho completo para o arquivo de instalação autônoma a ser associado às imagens que estão sendo adicionadas. Se **/SingleImage** não for especificado, o mesmo arquivo autônomo será associado a todas as imagens no arquivo. wim.|
## <a name="BKMK_examples"></a>Disso
Para adicionar uma imagem de inicialização, digite:
```
wdsutil /add-ImagmediaFile:"C:\MyFolder\Boot.wimmediatype:Boot
wdsutil /verbose /Progress /add-ImagmediaFile:\\MyServer\Share\Boot.wim /Server:MyWDSServemediatype:Boot /Name:"My WinPE Image" 
/Description:"WinPE Image containing the WDS Client" /Filename:WDSBoot.wim
```
Para adicionar uma imagem de instalação, digite uma das seguintes opções:
```
wdsutil /add-ImagmediaFile:"C:\MyFolder\Install.wimmediatype:Install
wdsutil /verbose /Progress /add-ImagmediaFile:\\MyServer\Share \Install.wim /Server:MyWDSServemediatype:InstalmediaGroup:ImageGroup1 
/SingleImage:"Windows Pro" /Name:"My WDS Image"
/Description:"Windows Pro image with Microsoft Office" /Filename:"Win Pro.wim" /UnattendFile:"\\server\share\unattend.xml"
```
#### <a name="additional-references"></a>Referências adicionais
A [chave de sintaxe de linha de comando](command-line-syntax-key.md)
[usando o comando copy-Image](using-the-copy-image-command.md)
[usando o comando Export-Image](using-the-export-image-command.md)
[usando o comando Get-Image](using-the-get-image-command.md)
[usando o comando Remove-Image](using-the-remove-image-command.md)
[usando o substituir o comando de imagem](using-the-replace-image-command.md)1[subcomando: Set-Image](subcommand-set-image.md)
