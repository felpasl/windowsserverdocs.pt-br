---
title: volume online
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5da073fd-578d-4691-ad0f-605ba66e0c7e
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 06a3c81313180b2880c1e47c3b6c12236fda4245
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71372521"
---
# <a name="online-volume"></a>volume online



Coloca os volumes que estão offline no momento para um estado online

> [!IMPORTANT]
> Esse comando não está disponível em nenhuma edição do Windows Vista.

> [!IMPORTANT]
> Esse comando falhará se for usado em um volume somente leitura.

## <a name="syntax"></a>Sintaxe

```
online volume [noerr]
```

## <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|NOERR|Somente para scripts. Quando um erro é encontrado, o DiskPart continua processando comandos como se o erro não tivesse ocorrido. Sem esse parâmetro, um erro faz com que o DiskPart saia com um código de erro.|

## <a name="remarks"></a>Comentários

-   Este comando opera em volumes que falharam, estão falhando ou estão em estado de redundância com falha.
-   Um volume deve ser selecionado para que esse comando tenha sucesso. Use o comando **selecionar volume** para selecionar um volume e deslocar o foco para ele.

## <a name="BKMK_examples"></a>Disso

Para colocar o volume com foco online, digite:
```
online volume
```

#### <a name="additional-references"></a>Referências adicionais

[Chave da sintaxe de linha de comando](command-line-syntax-key.md)

