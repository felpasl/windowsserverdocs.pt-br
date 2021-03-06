---
title: Usando o comando Remove-namespace
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 4eb758b6-8519-4e26-9fe0-2e19bb0e8702
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: b4c087442c43fd885fe4554cb29f9b2788420e05
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71362795"
---
# <a name="using-the-remove-namespace-command"></a>Usando o comando Remove-namespace

>Aplicável a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Remove um namespace personalizado.
## <a name="syntax"></a>Sintaxe
```
wdsutil /remove-Namespace /Namespace:<Namespace name> [/Server:<Server name>] [/force]
```
## <a name="parameters"></a>Parâmetros
|Parâmetro|Descrição|
|-------|--------|
|/Namespace:<Namespace name>|Especifica o nome do namespace. Esse não é o nome amigável e deve ser exclusivo.<br /><br />-   **serviço de função do servidor de implantação**: a sintaxe para o nome do namespace é/namespace: WDS:<ImageGroup>/<ImageName>/<Index>. Por exemplo: **WDS: ImageGroup1/install. wim/1**<br />**serviço de função de servidor de transporte**-   : esse valor deve corresponder ao nome fornecido para o namespace quando ele foi criado no servidor.|
|[/Server:<Server name>]|Especifica o nome do servidor. Esse pode ser o nome NetBIOS ou o FQDN (nome de domínio totalmente qualificado). Se nenhum nome de servidor for especificado, o servidor local será usado.|
|/Force|Remove o namespace imediatamente e encerra todos os clientes. Observe que, a menos que você especifique **/Force**, os clientes existentes poderão concluir a transferência, mas novos clientes não poderão ingressar.|
## <a name="BKMK_examples"></a>Disso
Para interromper um namespace (os clientes atuais podem concluir a transferência, mas novos clientes não podem ingressar), digite:
```
wdsutil /remove-Namespace /Namespace:"Custom Auto 1"
```
Para forçar o encerramento de todos os clientes, digite:
```
wdsutil /remove-Namespace /Server:MyWDSServer /Namespace:"Custom Auto 1" /force
```
#### <a name="additional-references"></a>referências adicionais
A [chave de sintaxe de linha de comando](command-line-syntax-key.md)
[usando o comando Get-mynamespaces](using-the-get-allnamespaces-command.md)
[usando o comando New-namespace](using-the-new-namespace-command.md)
[subcomando: Start-namespace](subcommand-start-namespace.md)
