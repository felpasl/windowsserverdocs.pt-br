---
title: Usando o comando Remove-Image
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ce5e2384-2264-4b22-92af-74eec8c10ae0
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: c0876649a4de55604707f03ca98cf0ceed2920b9
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71362851"
---
# <a name="using-the-remove-image-command"></a>Usando o comando Remove-Image

>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

exclui uma imagem de um servidor.
## <a name="syntax"></a>Sintaxe
para imagens de inicialização:
```
wdsutil [Options] /remove-Imagmedia:<Image name> [/Server:<Server name>mediatype:Boot /Architecture:{x86 | ia64 | x64} [/Filename:<Filename>]
```
para imagens de instalação:
```
wdsutil [Options] /remove-Imagmedia:<Image name> [/Server:<Server name>mediatype:InstallmediaGroup:<Image group name>] [/Filename:<Filename>]
```
## <a name="parameters"></a>Parâmetros
|Parâmetro|Descrição|
|-------|--------|
mídia: <Image name>|Especifica o nome da imagem.|
|[/Server:<Server name>]|Especifica o nome do servidor. Pode ser o nome NetBIOS ou o FQDN (nome de domínio totalmente qualificado). Se nenhum nome de servidor for especificado, o servidor local será usado.|
MediaType: {instalação &#124; de inicialização}|Especifica o tipo de imagem.|
|/Architecture: {x86 &#124; IA64 &#124; x64}|Especifica a arquitetura da imagem. Como é possível ter o mesmo nome de imagem para diferentes imagens de inicialização em diferentes arquiteturas, especificar o valor da arquitetura garante que a imagem correta será removida.|
|\mediaGroup: <Image group name>]|Especifica o grupo de imagens que contém a imagem. Se nenhum nome de grupo de imagens for especificado e houver apenas um grupo de imagens no servidor, esse grupo de imagens será usado. Se houver mais de um grupo de imagens, você deverá usar essa opção para especificar o grupo de imagens.|
|[/Filename:<File name>]|se a imagem não puder ser identificada exclusivamente pelo nome, você deverá usar essa opção para especificar o nome do arquivo.|
## <a name="BKMK_examples"></a>Disso
Para remover uma imagem de inicialização, digite:
```
wdsutil /remove-Imagmedia:"WinPE Boot Imagemediatype:Boot /Architecture:x86
```
```
wdsutil /verbose /remove-Imagmedia:"WinPE Boot Image" /Server:MyWDSServemediatype:Boot /Architecture:x64 /Filename:boot.wim
```
Para remover uma imagem de instalação, digite:
```
wdsutil /remove-Imagmedia:"Windows Vista with Officemediatype:Install
```
```
wdsutil /verbose /remove-Imagmedia:"Windows Vista with Office" /Server:MyWDSServemediatype:InstalmediaGroup:ImageGroup1 /Filename:install.wim
```
#### <a name="additional-references"></a>Referências adicionais
A [chave de sintaxe de linha de comando](command-line-syntax-key.md)
[usando o comando add-Image](using-the-add-image-command.md)
[usando o comando copy-Image](using-the-copy-image-command.md)
[usando o comando Export-Image](using-the-export-image-command.md)
[usando o comando Get-Image](using-the-get-image-command.md)
[usando o substituir o comando de imagem](using-the-replace-image-command.md)1[subcomando: Set-Image](subcommand-set-image.md)
