---
ms.assetid: fb95c8ee-a418-4520-a12a-7754ae947c3c
title: Fsutil reparsepoint
ms.prod: windows-server
manager: dmoss
ms.author: toklima
author: toklima
ms.technology: storage
audience: IT Pro
ms.topic: article
ms.date: 10/16/2017
ms.openlocfilehash: fe274ad9a6dffc72607102d3430ba7527d3cc558
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71376846"
---
# <a name="fsutil-reparsepoint"></a>Fsutil reparsepoint
>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows 10, Windows Server 2012 R2, Windows 8.1, Windows Server 2012, Windows 8, Windows Server 2008 R2, Windows 7, Windows 2008, Windows Vista

Consulta ou exclui pontos de nova análise.  O comando **fsutil reparsepoint** normalmente é usado por profissionais de suporte.

Para obter exemplos de como usar esse comando, consulte [Exemplos](#BKMK_examples).

## <a name="syntax"></a>Sintaxe

```
fsutil reparsepoint [query] <FileName>
fsutil reparsepoint [delete] <FileName>
```

## <a name="parameters"></a>Parâmetros

| Parâmetro  |                                                                Descrição                                                                |
|------------|-------------------------------------------------------------------------------------------------------------------------------------------|
|   query    |            Recupera os dados do ponto de nova análise que estão associados ao arquivo ou diretório identificado pelo identificador especificado.             |
|   delete   | Exclui um ponto de nova análise do arquivo ou diretório que é identificado pelo identificador especificado, mas não exclui o arquivo ou diretório. |
| <FileName> |             Especifica o caminho completo para o arquivo, incluindo o nome do arquivo e a extensão, por exemplo, C:\documents\filename.txt.             |

## <a name="remarks"></a>Comentários

-   Pontos de nova análise são objetos do sistema de arquivos NTFS que têm um atributo definíveis que contém dados definidos pelo usuário e são usados para estender a funcionalidade no subsistema de entrada/saída (e/s).

-   Pontos de nova análise são usados para pontos de junção de diretório e pontos de montagem de volume. Eles também são usados por drivers de filtro do sistema de arquivos para marcar determinados arquivos como especiais para esse driver.

-   Quando um programa define um ponto de nova análise, ele armazena esses dados, além de uma marca de nova análise, que identifica exclusivamente os dados que estão sendo armazenados. Quando o sistema de arquivos abre um arquivo com um ponto de nova análise, ele tenta localizar o filtro do sistema de arquivos associado. Se o filtro do sistema de arquivos for encontrado, o filtro processará o arquivo conforme direcionado pelos dados de nova análise. Se nenhum filtro do sistema de arquivos for encontrado, a operação de abertura de arquivo falhará.

## <a name="BKMK_examples"></a>Disso
Para recuperar os dados do ponto de nova análise associados ao C:\Server, digite:

```
fsutil reparsepoint query c:\server
```

Para excluir um ponto de nova análise de um arquivo ou diretório especificado, use o seguinte formato:

```
fsutil reparsepoint delete c:\server
```

#### <a name="additional-references"></a>Referências adicionais
[Chave da sintaxe de linha de comando](Command-Line-Syntax-Key.md)

[Fsutil](Fsutil.md)


