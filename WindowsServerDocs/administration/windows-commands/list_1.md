---
title: lista
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 69b105a1-9710-4a06-8102-38cc9e475ca5
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: a9ac8b19ecae30c339138f61a13c21147d4bcf1b
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71374650"
---
# <a name="list"></a>lista



Exibe uma lista de discos, de partições em um disco, de volumes em um disco ou de VHDs (discos rígidos virtuais).

## <a name="syntax"></a>Sintaxe

```
list { disk | partition | volume | vdisk }
```

## <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|disco|Exibe uma lista de discos e informações sobre eles, como seu tamanho, a quantidade de espaço livre disponível, se o disco é um disco básico ou dinâmico e se o disco usa o MBR (registro mestre de inicialização) ou o estilo de partição GPT (tabela de partição GUID).|
|partição|Exibe as partições listadas na tabela de partição do disco atual.|
|volume|Exibe uma lista dos volumes básicos e dinâmicos em todos os discos.|
|vdisk|Exibe uma lista dos VHDs que estão anexados e/ou selecionados. Este comando lista os VHDs desanexados se eles estiverem selecionados no momento; no entanto, o tipo de disco é definido como desconhecido até que o VHD seja anexado. O VHD marcado com um asterisco (*) tem foco.</br>Observação: Este comando só está disponível para o Windows 7 e o Windows Server 2008 R2.|

## <a name="remarks"></a>Comentários

-   Ao Listar partições em um disco dinâmico, as partições podem não corresponder aos volumes dinâmicos no disco. Essa discrepância ocorre porque os discos dinâmicos contêm entradas na tabela de partição do volume do sistema ou do volume de inicialização (se estiver presente no disco). Eles também contêm uma partição que ocupa o restante do disco para reservar o espaço para uso por volumes dinâmicos.
-   O objeto marcado com um asterisco (*) tem foco.
-   Ao listar discos, se um disco estiver ausente, seu número de disco será prefixado com M. Por exemplo, o primeiro disco ausente é numerado M0.

## <a name="BKMK_examples"></a>Disso

```
list disk
list partition
list volume
list vdisk
```

#### <a name="additional-references"></a>Referências adicionais

[Chave da sintaxe de linha de comando](command-line-syntax-key.md)

