---
title: pushd
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 396bc545-0f41-473e-b0ac-76fbbb74d390
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 634dd6dee471751cc62b6899a3963e02e8e783a2
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71371983"
---
# <a name="pushd"></a>pushd



Armazena o diretório atual para uso pelo comando **popd** e, em seguida, altera para o diretório especificado.

Para obter exemplos de como usar esse comando, consulte [Exemplos](#BKMK_examples).

## <a name="syntax"></a>Sintaxe

```
pushd [<Path>]
```

## <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|\<Path >|Especifica o diretório para tornar o diretório atual. Este comando dá suporte a caminhos relativos.|
|/?|Exibe a ajuda no prompt de comando.|

## <a name="remarks"></a>Comentários

-   Sempre que você usa o comando **PUSHD** , um único diretório é armazenado para seu uso. No entanto, você pode armazenar vários diretórios usando o comando **PUSHD** várias vezes.

    Os diretórios são armazenados em sequência em uma pilha virtual. Se você usar o comando **PUSHD** uma vez, o diretório no qual você usa o comando será colocado na parte inferior da pilha. Se você usar o comando novamente, o segundo diretório será colocado na parte superior do primeiro. O processo é repetido sempre que você usa o comando **PUSHD** .

    Você pode usar o comando **popd** para alterar o diretório atual para o diretório armazenado mais recentemente pelo comando **Pushed** . Se você usar o comando **popd** , o diretório na parte superior da pilha será removido da pilha e o diretório atual será alterado para esse diretório. Se você usar o comando **popd** novamente, o próximo diretório na pilha será removido.
-   Se as extensões de comando estiverem habilitadas, o comando **PUSHD** aceitará um caminho de rede ou uma letra de unidade local e um caminho.
-   Se você especificar um caminho de rede, o comando **Pushed** atribuirá temporariamente a letra de unidade não utilizada mais alta (começando com Z:) para o recurso de rede especificado. O comando altera a unidade e o diretório atuais para o diretório especificado na unidade atribuída recentemente. Se você usar o comando **popd** com extensões de comando habilitadas, o comando **popd** removerá a atribuição de letra da unidade criada por **PUSHD**.

## <a name="BKMK_examples"></a>Disso

O exemplo a seguir mostra como você pode usar o comando **Pushed** e o comando **popd** em um programa em lotes para alterar o diretório atual daquele em que o programa em lotes foi executado e, em seguida, alterá-lo novamente:
```
@echo off
rem This batch file deletes all .txt files in a specified directory
pushd %1
del *.txt
popd
cls
echo All text files deleted in the %1 directory
```

#### <a name="additional-references"></a>Referências adicionais

[Chave da sintaxe de linha de comando](command-line-syntax-key.md)

[Popd](popd.md)