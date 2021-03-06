---
title: wscript
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2fbaf193-cdbd-414c-84c9-bb5720f84c29
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 08/21/2018
ms.openlocfilehash: 5e33f3f626ddb2645643ef3bfa8971667f692295
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71361797"
---
# <a name="wscript"></a>wscript



O Windows Script Host fornece um ambiente no qual os usuários podem executar scripts em uma variedade de idiomas que usam uma variedade de modelos de objeto para executar tarefas.

## <a name="syntax"></a>Sintaxe

```
wscript [<scriptname>] [/b] [/d] [/e:<engine>] [{/h:cscript|/h:wscript}] [/i] [/job:<identifier>] [{/logo|/nologo}] [/s] [/t:<number>] [/x] [/?] [<ScriptArguments>]
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|scriptname|Especifica o caminho e o nome do arquivo de script.|
|/b.|Especifica o modo de lote, que não exibe alertas, erros de script ou prompts de entrada. Esse é o oposto de **/i**.|
|/d|Inicia o depurador.|
|/e|Especifica o mecanismo usado para executar o script. Isso permite executar scripts que usam uma extensão de nome de arquivo personalizado. Sem o parâmetro/e, você só pode executar scripts que usam extensões de nome de arquivo registrado. Por exemplo, se você tentar executar este comando:<br>```cscript test.admin```<br>Você receberá esta mensagem de erro: Erro de entrada: Não há mecanismo de script para a extensão de arquivo ". admin".<br>Uma vantagem de usar extensões de nome de arquivo não padrão é que ele protege contra o clique duplo de um script e a execução de algo que você realmente não queria executar. <br>Isso não cria uma associação permanente entre a extensão de nome de arquivo. admin e o VBScript. Cada vez que você executar um script que usa uma extensão de nome de arquivo. admin, será necessário usar o parâmetro/e.|
|/h: cscript|Registra o **cscript. exe** como o host de script padrão para executar scripts.|
|/h: WScript|Registra o **WScript. exe** como o host de script padrão para executar scripts. Esse é o padrão quando a opção **/h** é omitida.|
|/i|Especifica o modo interativo, que exibe alertas, erros de script e prompts de entrada.</br>Esse é o padrão e o oposto de **/b**.|
|/minuto: \<identifier >|Executa o trabalho identificado pelo *identificador* em um arquivo de script **. wsf** .|
|/logo|Especifica que a faixa do host de scripts do Windows é exibida no console do antes de o script ser executado.</br>Esse é o padrão e o oposto de **/nologo**.|
|/nologo|Especifica que a faixa do host de scripts do Windows não é exibida antes de o script ser executado. Esse é o oposto de **/logo**.|
|/s|Salva as opções de prompt de comando atuais do usuário atual.|
|/t: \<number >|Especifica o tempo máximo que o script pode executar (em segundos). Você pode especificar até 32.767 segundos.</br>O padrão é sem limite de tempo.|
|/x|Inicia o script no depurador.|
|ScriptArguments|Especifica os argumentos passados para o script. Cada argumento de script deve ser precedido por uma barra (/).|
|/?|Exibe a ajuda no prompt de comando.|

## <a name="remarks"></a>Comentários

-   A execução dessa tarefa não requer que você tenha credenciais administrativas. Portanto, como a prática recomendada de segurança, considere executar essa tarefa como um usuário sem credenciais administrativas.
-   Para abrir um prompt de comando, na tela **Inicial**, digite **cmd** e clique em **prompt de comando**.
-   Cada parâmetro é opcional; no entanto, você não pode especificar argumentos de script sem especificar um script. Se você não especificar um script ou nenhum argumento de script, o **WScript. exe** exibirá a caixa de diálogo **configurações do host de scripts do Windows** , que pode ser usada para definir propriedades de script globais para todos os scripts que o **WScript. exe** executa no computador local.
-   O parâmetro **/t** impede a execução excessiva de scripts por meio da definição de um temporizador. Quando o tempo excede o valor especificado, o **WScript** interrompe o mecanismo de script e encerra o processo.
-   Os arquivos de script do Windows geralmente têm uma das seguintes extensões de nome de arquivo: **. wsf**, **. vbs**, **. js**.
-   Se você clicar duas vezes em um arquivo de script com uma extensão que não tem associação, a caixa de diálogo **abrir com** será exibida. Selecione **WScript** ou **cscript**e, em seguida, selecione **sempre usar este programa para abrir este tipo de arquivo**. Isso registra o **WScript. exe** ou o **cscript. exe** como o host de script padrão para arquivos desse tipo de arquivo.
-   Você pode definir propriedades para scripts individuais. Consulte [visão geral do Windows Script Host](https://technet.microsoft.com/library/cc738350(v=ws.10).aspx) para obter mais informações.
-   O Windows Script Host pode usar arquivos de script **. wsf** . Cada arquivo **. wsf** pode usar vários mecanismos de script e executar vários trabalhos.

#### <a name="additional-references"></a>Referências adicionais

-   [Chave da sintaxe de linha de comando](command-line-syntax-key.md)
