---
title: tzutil
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: bcf6e007-c9b6-4df5-83c5-ed7b4b1b5913
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 347254bd5a00a8bfb4a80f20d518f1e0e8b593bf
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392308"
---
# <a name="tzutil"></a>tzutil

>Aplicável a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Exibe o utilitário de fuso horário do Windows. 
## <a name="syntax"></a>Sintaxe
```
tzutil [/?] [/g] [/s <timeZoneID>[_dstoff]] [/l]
```
### <a name="parameters"></a>Parâmetros
|Parâmetro|Descrição|
|-------|--------|
|/?|Exibe a ajuda no prompt de comando.|
|/g|Exibe a ID do fuso horário atual.|
|/s \<TimeZoneID > [_dstoff]|Define o fuso horário atual usando a ID de fuso horário especificada. O sufixo **_dstoff** desabilita os ajustes de horário de verão para o fuso horário (quando aplicável).|
|/l|lista todas as IDs de fuso horário e nomes de exibição válidos. A saída será:<br /><br />-   \<nome de exibição ><br />-   \<ID de fuso horário >|

## <a name="remarks"></a>Comentários
Um código de saída **0** indica que o comando foi concluído com êxito.

## <a name="BKMK_Examples"></a>Disso
Para exibir a ID do fuso horário atual, digite:
```
tzutil /g
```
Para definir o fuso horário atual como hora padrão do Pacífico, digite:
```
tzutil /s Pacific Standard time
```
Para definir o fuso horário atual como hora padrão do Pacífico e desabilitar os ajustes de horário de verão, digite:
```
tzutil /s Pacific Standard time_dstoff
```
## <a name="additional-references"></a>referências adicionais
-   [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

