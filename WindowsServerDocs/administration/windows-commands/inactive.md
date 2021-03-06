---
title: Inativo
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f4fb4695-4e66-4166-b4ab-2c86a4605580
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 9ce91b6a024c165e3aa63148b9ad6dfcc4db7a7c
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71375367"
---
# <a name="inactive"></a>Inativo



Em discos básicos de MBR (registro mestre de inicialização), o marca a partição do sistema ou a partição de inicialização com foco como inativa.

## <a name="syntax"></a>Sintaxe

```
inactive
```

## <a name="remarks"></a>Comentários

> [!CAUTION]
> Seu computador pode não iniciar sem uma partição ativa. Não marque uma partição de inicialização ou de sistema como inativa, a menos que você seja um usuário experiente com uma compreensão completa da família de sistemas operacionais Windows.</br>> Se não for possível iniciar o computador depois de marcar o sistema ou a partição de inicialização como inativa, insira o CD do Instalação do Windows na unidade de CD-ROM, reinicie o computador e repare a partição usando os comandos **FIXMBR** e **fixboot** no Console de recuperação.
> -   Depois de marcar a partição do sistema ou a partição de inicialização como inativa, seu computador será iniciado da próxima opção especificada no BIOS, como a unidade de CD-ROM ou um PXE (Pre-Boot eXecution Environment).
> -   Um sistema ativo ou uma partição de inicialização deve ser selecionada para que essa operação seja realizada com sucesso. Use o comando **selecionar partição** para selecionar a partição ativa e deslocar o foco para ela.

## <a name="BKMK_examples"></a>Disso

```
inactive
```

#### <a name="additional-references"></a>Referências adicionais

[Chave da sintaxe de linha de comando](command-line-syntax-key.md)

