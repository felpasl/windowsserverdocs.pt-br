---
title: msinfo32
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a38f31d7-1766-4103-becc-9d0b87c2826d
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 9ec08171816476cf04bbfb70637ff8253192e21b
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71373385"
---
# <a name="msinfo32"></a>msinfo32

>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Abre a ferramenta de informações do sistema para exibir uma visão abrangente do hardware, dos componentes do sistema e do ambiente de software no computador local. 
## <a name="syntax"></a>Sintaxe
```
msinfo32 [/pch] [/nfo <path>] [/report <path>] [/computer <computerName>] [/showcategories] [/category <CategoryID>] [/categories {+<CategoryID>(+<CategoryID>)|+all(-<CategoryID>)}]
```
### <a name="parameters"></a>Parâmetros

|    Parâmetro    |                                                                                                                                 Descrição                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <path>      | Especifica o arquivo a ser aberto no formato *C:\Folder1\File1.xxx*, em que *C* é a letra da unidade, *Pasta1* é a pasta, *arquivo1* é o nome do arquivo e *xxx* é a extensão de nome de arquivo.<br /><br />Esse arquivo pode ser um arquivo **. NFO**, **. xml**, **. txt**ou **. cab** . |
| <computerName>  |                                                                             Especifica o nome do computador local ou de destino. Pode ser um nome UNC, um endereço IP ou um nome de computador completo.                                                                              |
|  <CategoryID>   |                                                                                     Especifica a ID do item de categoria. Você pode obter a ID da categoria usando **/showcategories**.                                                                                      |
|      /pch       |                                                                                                       Exibe a exibição do histórico do sistema na ferramenta de informações do sistema.                                                                                                       |
|      /nfo       |                                     Salva o arquivo exportado como um arquivo **. NFO** . Se o nome do arquivo especificado no *caminho* não terminar em uma extensão **. NFO** , a extensão **. NFO** será anexada automaticamente ao nome do arquivo.                                      |
|     /Report     |                                               Salva o arquivo no *caminho* como um arquivo de texto. O nome do arquivo é salvo exatamente como aparece no *caminho*. A extensão. txt não é anexada ao arquivo, a menos que seja especificado no caminho.                                                |
|    /computer    |                                                                inicia a ferramenta de informações do sistema para o computador remoto especificado. Você deve ter as permissões apropriadas para acessar o computador remoto.                                                                |
| /showcategories |                         inicia a ferramenta de informações do sistema com todas as IDs de categoria disponíveis exibidas, em vez de exibir os nomes amigáveis ou localizados. Por exemplo, a categoria de ambiente de software é exibida como a categoria **SWEnv** .                         |
|    /Category    |                                                                     inicia as informações do sistema com a categoria especificada selecionada. Use **/showcategories** para exibir uma lista de IDs de categoria disponíveis.                                                                     |
|   /categories   |                          inicia as informações do sistema apenas com a categoria ou categorias especificadas exibidas. Ele também limita a saída para a categoria ou categorias selecionadas. Use **/showcategories** para exibir uma lista de IDs de categoria disponíveis.                          |
|       /?        |                                                                                                                     Exibe a ajuda no prompt de comando.                                                                                                                     |

## <a name="remarks"></a>Comentários
Algumas categorias de informações do sistema contêm grandes quantidades de dados. Você pode usar o comando **Start/Wait** para otimizar o desempenho de relatórios para essas categorias. Para obter mais informações, consulte [informações do sistema](https://technet.microsoft.com/library/cc783305(v=ws.10).aspx).
## <a name="BKMK_Examples"></a>Disso
Para listar as IDs de categoria disponíveis, digite:
```
msinfo32 /showcategories
```
Para iniciar a ferramenta de informações do sistema com todas as informações disponíveis exibidas, exceto os módulos carregados, digite:
```
msinfo32 /categories +all -loadedmodules
```
Para exibir apenas informações de resumo do sistema e criar um arquivo. NFO chamado syssum. NFO que contém informações na categoria Resumo do sistema, digite:
```
msinfo32 /nfo syssum.nfo /categories +systemsummary
```
Para exibir informações de conflito de recursos e criar um arquivo. NFO chamado Conflicts. NFO que contém informações sobre conflitos de recursos, digite:
```
msinfo32 /nfo conflicts.nfo /categories    +componentsproblemdevices+resourcesconflicts+resourcesforcedhardware
```
## <a name="additional-references"></a>Referências adicionais
-   [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

