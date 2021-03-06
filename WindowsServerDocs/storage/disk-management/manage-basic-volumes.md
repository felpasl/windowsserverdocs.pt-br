---
title: Gerenciar volumes básicos
description: Este artigo descreve como gerenciar volumes básicos.
ms.date: 10/12/2017
ms.prod: windows-server
ms.technology: storage
ms.topic: article
author: JasonGerend
manager: brianlic
ms.author: jgerend
ms.openlocfilehash: 2eee5820891c108475c58c9ad024cd7c00391e43
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71385916"
---
# <a name="manage-basic-volumes"></a>Gerenciar volumes básicos

> **Aplicável a:** Windows 10, Windows 8.1, Windows Server (Canal Semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Um disco básico é um disco físico contendo partições primárias, estendidas ou unidades lógicas. Partições e unidades lógicas em discos básicos são conhecidas como volumes básicos. Você pode criar volumes básicos somente em discos básicos.

É possível adicionar mais espaço às partições primárias e lógicas existentes estendendo-as para um espaço não alocado adjacente e contíguo no mesmo disco. Para estender um volume básico, ele deve ser formatado com o sistema de arquivos NTFS. É possível estender uma unidade lógica no espaço livre contíguo na partição estendida que contém essa unidade. Se você estender uma unidade lógica além do espaço livre disponível na partição estendida, esta aumenta para conter a unidade lógica, contanto que a partição estendida seja seguida por espaço não alocado contíguo.

## <a name="see-also"></a>Consulte também

-   [Atribuir um caminho de pasta do ponto de montagem a uma unidade](assign-a-mount-point-folder-path-to-a-drive.md)
-   [Estender um volume básico](extend-a-basic-volume.md)
-   [Reduzir um volume básico](shrink-a-basic-volume.md)