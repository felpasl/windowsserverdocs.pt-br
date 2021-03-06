---
title: ntbackup
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6bce6b0d-646b-46b6-b833-0ff1d6f082c2
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: ebbe71fd5547311beb36747d32d695823e0f0059
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71372685"
---
# <a name="ntbackup"></a>ntbackup



O comando **Ntbackup** não está disponível no Windows Vista ou no windows Server 2008. Em vez disso, você deve usar o comando **Wbadmin** e os subcomandos para fazer backup e restaurar o computador e os arquivos de um prompt de comando.

Não é possível recuperar backups criados com o **ntbackup** usando o **wbadmin**. No entanto, uma versão do **Ntbackup** está disponível como um download para os usuários do windows Server 2008 e do Windows Vista que desejam recuperar os backups criados usando o **Ntbackup**. Esta versão para download do **Ntbackup** permite que você execute recuperações apenas de backups herdados e não pode ser usada em computadores que executam o windows Server 2008 ou o Windows Vista para criar novos backups. Para baixar esta versão do **Ntbackup**, consulte [https://go.microsoft.com/fwlink/?LinkId=82917](https://go.microsoft.com/fwlink/?LinkId=82917).

#### <a name="additional-references"></a>Referências adicionais

[Chave da sintaxe de linha de comando](command-line-syntax-key.md)

[Wbadmin](wbadmin.md)