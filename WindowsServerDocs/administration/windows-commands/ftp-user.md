---
title: usuário de FTP
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0a77bfeb-27a9-4f2f-a3c4-2fef529fb569 vhorne
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 63281a0ffdd646d3652eb3a442a8edd9acec9cce
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71375872"
---
# <a name="ftp-user"></a>FTP: usuário

>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Especifica um usuário para o computador remoto.   
## <a name="syntax"></a>Sintaxe  
```  
user <UserName> [<Password>] [<Account>]  
```  
### <a name="parameters"></a>Parâmetros  

|  Parâmetro   |                                                                      Descrição                                                                      |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <UserName>  |                                          Especifica um nome de usuário com o qual fazer logon no computador remoto.                                           |
| [<Password>] |               Especifica a senha para o *nome de usuário*. Se uma senha não for especificada, mas for necessária, o **FTP** solicitará a senha.               |
| [<Account>]  | Especifica uma conta com a qual fazer logon no computador remoto. Se uma *conta* não for especificada, mas for necessária, o **FTP** solicitará a conta. |

## <a name="BKMK_Examples"></a>Disso  
Especifique user1 com a senha password1.  
```  
user User1 Password1  
```  
## <a name="additional-references"></a>Referências adicionais  
-   [Chave da sintaxe de linha de comando](command-line-syntax-key.md)  
