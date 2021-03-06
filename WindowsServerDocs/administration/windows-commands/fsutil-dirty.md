---
ms.assetid: 385a2a7c-d6bd-4f11-9c18-fca0413f9e97
title: Fsutil Dirty
ms.prod: windows-server
manager: dmoss
ms.author: toklima
author: toklima
ms.technology: storage
audience: IT Pro
ms.topic: article
ms.date: 10/16/2017
ms.openlocfilehash: 01b5490ef7c57e48a43cae15902e03a33794a826
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71377014"
---
# <a name="fsutil-dirty"></a>Fsutil Dirty
>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows 10, Windows Server 2012 R2, Windows 8.1, Windows Server 2012, Windows 8, Windows Server 2008 R2, Windows 7

Consulta ou define um bit sujo de volume. Quando o bit sujo de um volume é definido, o **autochk** verifica automaticamente o volume em busca de erros na próxima vez em que o computador for reiniciado.

Para obter exemplos de como usar esse comando, consulte [Exemplos](#BKMK_examples).

## <a name="syntax"></a>Sintaxe

```
fsutil dirty {query | set} <VolumePath>
```

## <a name="parameters"></a>Parâmetros

|   Parâmetro   |                                                 Descrição                                                  |
|---------------|--------------------------------------------------------------------------------------------------------------|
|     query     |                                  Consulta o bit sujo do volume especificado.                                   |
|      set      |                                    Define o bit sujo do volume especificado.                                    |
| \<VolumePath > | Especifica o nome da unidade seguido por dois-pontos ou GUID no seguinte formato: **Volume {** <em>GUID</em> **}** . |

## <a name="remarks"></a>Comentários

-   O bit sujo de um volume indica que o sistema de arquivos pode estar em um estado inconsistente. O bit sujo pode ser definido porque:

    -   O volume está online e tem alterações pendentes.

    -   Foram feitas alterações no volume e o computador foi desligado antes que as alterações fossem confirmadas no disco.

    -   Foi detectado um dano no volume.

-   Se o bit sujo for definido quando o computador for reiniciado, **chkdsk** será executado para verificar a integridade do sistema de arquivos e tentar corrigir quaisquer problemas com o volume.

## <a name="BKMK_examples"></a>Disso
Para consultar o bit sujo na unidade C, digite:

```
fsutil dirty query c:
```

-   Se o volume estiver sujo, a saída a seguir exibirá:

    `Volume C: is dirty`

-   Se o volume não estiver sujo, a saída a seguir exibirá:

    `Volume C: is not dirty`

Para definir o bit sujo na unidade C, digite:

```
fsutil dirty set C:
```

#### <a name="additional-references"></a>Referências adicionais
[Chave da sintaxe de linha de comando](Command-Line-Syntax-Key.md)

[Fsutil](Fsutil.md)


