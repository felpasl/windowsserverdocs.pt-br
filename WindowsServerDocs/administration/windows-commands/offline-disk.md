---
title: disco offline
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8fb9b3c3-0b2c-4192-a2e7-f706292653e3
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: f28d473cdb557d6adb3aaf235bebdfbc4e78b24a
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71372604"
---
# <a name="offline-disk"></a>disco offline



Coloca o disco online com foco no estado offline.

> [!IMPORTANT]
> Esse comando do DiskPart não está disponível em nenhuma edição do Windows Vista.

## <a name="syntax"></a>Sintaxe

```
offline disk [noerr]
```

## <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|NOERR|Somente para scripts. Quando um erro é encontrado, o DiskPart continua processando comandos como se o erro não tivesse ocorrido. Sem esse parâmetro, um erro faz com que o DiskPart saia com um código de erro.|

## <a name="remarks"></a>Comentários

-   Esse comando opera em discos que estão no modo SAN online. Ele altera seu modo SAN para offline.
-   Se um disco dinâmico em um grupo de discos for colocado offline, o status do disco será alterado para **ausente** e o grupo mostrará um disco que está offline. O disco ausente é movido para o grupo inválido. Se o disco dinâmico for o último disco do grupo, o status do disco será alterado para **offline**e o grupo vazio será removido.
-   Um disco deve ser selecionado para que o comando de **disco offline** seja executado com sucesso. Use o comando **selecionar disco** para selecionar um disco e deslocar o foco para ele.

## <a name="BKMK_examples"></a>Disso

Para colocar o disco com foco offline, digite:
```
offline disk
```

#### <a name="additional-references"></a>Referências adicionais

[Chave da sintaxe de linha de comando](command-line-syntax-key.md)

