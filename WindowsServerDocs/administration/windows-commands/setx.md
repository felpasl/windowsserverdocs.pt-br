---
title: setx
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ef37482f-f8a8-4765-951a-2518faac3f44
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: c206f36e2d0bc947329124b08fb797091e838bcd
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71384035"
---
# <a name="setx"></a>setx



Cria ou modifica variáveis de ambiente no ambiente do usuário ou do sistema, sem a necessidade de programação ou script. O comando **setx** também recupera os valores de chaves do registro e os grava em arquivos de texto.

Para obter exemplos de como usar esse comando, consulte [Exemplos](#BKMK_examples).

## <a name="syntax"></a>Sintaxe

```
setx [/s <Computer> [/u [<Domain>\]<User name> [/p [<Password>]]]] <Variable> <Value> [/m]
setx [/s <Computer> [/u [<Domain>\]<User name> [/p [<Password>]]]] [<Variable>] /k <Path> [/m]
setx [/s <Computer> [/u [<Domain>\]<User name> [/p [<Password>]]]] /f <FileName> {[<Variable>] {/a <X>,<Y> | /r <X>,<Y> "<String>"} [/m] | /x} [/d <Delimiters>]
```

## <a name="parameters"></a>Parâmetros

|         Parâmetro          |                                                                                                                                              Descrição                                                                                                                                              |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       /s \<computador >       |                                                                                  Especifica o nome ou o endereço IP de um computador remoto. Não use barras invertidas. O valor padrão é o nome do computador local.                                                                                  |
| /u [\<\]de domínio > <User name> |                                                                                           Executa o script com as credenciais da conta de usuário especificada. O valor padrão é as permissões do sistema.                                                                                            |
|      /p [\<a senha >]      |                                                                                                         Especifica a senha da conta de usuário que é especificada no parâmetro **/u** .                                                                                                         |
|        Variável de \<>         |                                                                                                                 Especifica o nome da variável de ambiente que você deseja definir.                                                                                                                  |
|          \<valor >          |                                                                                                                Especifica o valor para o qual você deseja definir a variável de ambiente.                                                                                                                 |
|         /k \<caminho >         | Especifica que a variável é definida com base nas informações de uma chave do registro. O p*Ho* usa a seguinte sintaxe:</br>`\\<HIVE>\<KEY>\...\<Value>`</br>Por exemplo, você pode especificar o seguinte caminho:</br>`HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TimeZoneInformation\StandardName` |
|      /f \<nome do arquivo >       |                                                                                                                               Especifica o arquivo que você deseja usar.                                                                                                                                |
|        /a \<X ><Y>         |                                                                                                                    Especifica coordenadas absolutas e deslocamento como parâmetros de pesquisa.                                                                                                                    |
|   /r \<X ><Y> "<String>"   |                                                                                                            Especifica as coordenadas relativas e o deslocamento da **cadeia de caracteres** como parâmetros de pesquisa.                                                                                                            |
|             /m             |                                                                                                Especifica a definição da variável no ambiente do sistema. A configuração padrão é o ambiente local.                                                                                                 |
|             /x             |                                                                                                       Exibe as coordenadas do arquivo, ignorando as opções de linha de comando **/a**, **/r**e **/d** .                                                                                                        |
|      /d \<delimitadores >      |                    Especifica os delimitadores, como " **,** " ou " **\\** ", a serem usados, além dos quatro delimitadores internos — espaço, tabulação, Enter e avanço de discagem. Os delimitadores válidos incluem qualquer caractere ASCII. O número máximo de delimitadores é 15, incluindo delimitadores internos.                    |
|             /?             |                                                                                                                                 Exibe a ajuda no prompt de comando.                                                                                                                                  |

## <a name="remarks"></a>Comentários

-   O comando **setx** é semelhante ao utilitário UNIX setenv.
-   **Setx** fornece a única linha de comando ou a maneira programática de definir de forma direta e permanente valores de ambiente do sistema. Variáveis de ambiente do sistema são manualmente configuráveis por meio do **painel de controle** ou por meio de um editor do registro. O comando **set** , que é interno ao interpretador de comandos (cmd. exe), define as variáveis de ambiente do usuário somente para a janela de console atual.
-   Você pode usar o comando **setx** para definir valores para variáveis de ambiente do usuário e do sistema de uma das três fontes (modos): modo de linha de comando, modo de registro ou modo de arquivo.
-   **Setx** grava variáveis no ambiente mestre no registro. As variáveis definidas com variáveis **setx** só estão disponíveis em janelas de comando futuras, não na janela de comando atual.
-   **HKEY_CURRENT_USER** e **HKEY_LOCAL_MACHINE** são os únicos Hives com suporte. REG_DWORD, REG_EXPAND_SZ, REG_SZ e REG_MULTI_SZ são os tipos de dados de **RegKey** válidos.
-   Quando você obter acesso a **REG_MULTI_SZ** valores no registro, somente o primeiro item será extraído e usado.
-   Você não pode usar o comando **setx** para remover valores que foram adicionados aos ambientes locais ou do sistema. Você pode usar **set** com um nome de variável e nenhum valor para remover um valor correspondente do ambiente local.
-   REG_DWORD valores do registro são extraídos e usados no modo hexadecimal.
-   O modo de arquivo dá suporte apenas à análise de arquivos de texto de retorno de carro e alimentação de linha (CRLF).

## <a name="BKMK_examples"></a>Disso

Para definir a variável de ambiente de computador no ambiente local para o valor Brand1, digite:
```
setx MACHINE Brand1
```
Para definir a variável de ambiente do computador no ambiente do sistema para o valor Brand1 computador, digite:
```
setx MACHINE "Brand1 Computer" /m
```
Para definir a variável de ambiente MYPATH no ambiente local para usar o caminho de pesquisa definido na variável de ambiente PATH, digite:
```
setx MYPATH %PATH%
```
Para definir a variável de ambiente MYPATH no ambiente local para usar o caminho de pesquisa definido na variável de ambiente PATH depois de substituir **~** por **%** , digite:
```
setx MYPATH ~PATH~ 
```
Para definir a variável de ambiente do computador no ambiente local como Brand1 em um computador remoto chamado Computador1, digite:
```
setx /s computer1 /u maindom\hiropln /p p@ssW23 MACHINE Brand1
```
Para definir a variável de ambiente MYPATH no ambiente local para usar o caminho de pesquisa definido na variável de ambiente PATH em um computador remoto chamado Computador1, digite:
```
setx /s computer1 /u maindom\hiropln /p p@ssW23 MYPATH %PATH%
```
Para definir a variável de ambiente TZONE no ambiente local com o valor encontrado na chave do registro **HKEY_LOCAL_MACHINE \system\currentcontrolset\control\timezoneinformation\standardname** , digite:
```
setx TZONE /k HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TimeZoneInformation\StandardName 
```
Para definir a variável de ambiente TZONE no ambiente local de um computador remoto chamado Computador1 com o valor encontrado na chave do registro **HKEY_LOCAL_MACHINE \system\currentcontrolset\control\timezoneinformation\standardname** , digite:
```
setx /s computer1 /u maindom\hiropln /p p@ssW23 TZONE /k HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TimeZoneInformation\StandardName 
```
Para definir a variável de ambiente BUILD no ambiente do sistema com o valor encontrado na chave do registro **HKEY_LOCAL_MACHINE \software\microsoft\windowsnt\currentversion\currentbuildnumber** , digite:
```
setx BUILD /k "HKEY_LOCAL_MACHINE\Software\Microsoft\WindowsNT\CurrentVersion\CurrentBuildNumber" /m
```
Para definir a variável de ambiente BUILD no ambiente do sistema de um computador remoto chamado Computador1 com o valor encontrado na chave do registro **HKEY_LOCAL_MACHINE \software\microsoft\windowsnt\currentversion\currentbuildnumber** , digite:
```
setx /s computer1 /u maindom\hiropln /p p@ssW23  BUILD /k "HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\CurrentBuildNumber" /m
```
Para exibir o conteúdo de um arquivo chamado ipconfig. out, juntamente com as coordenadas correspondentes do conteúdo, digite:
```
setx /f ipconfig.out /x
```
Para definir a variável de ambiente IPADDR no ambiente local para o valor encontrado na coordenada 5, 11 no arquivo ipconfig. out, digite:
```
setx IPADDR /f ipconfig.out /a 5,11
```
Para definir a variável de ambiente OCTET1 no ambiente local para o valor encontrado na coordenada 5, 3 no arquivo ipconfig. out com delimitadores **"# $\*."** , digite:
```
setx OCTET1 /f ipconfig.out /a 5,3 /d "#$*." 
```
Para definir a variável de ambiente IPGATEWAY no ambiente local para o valor encontrado na coordenada 0, 7 em relação à coordenada de "gateway" no arquivo ipconfig. out, digite:
```
setx IPGATEWAY /f ipconfig.out /r 0,7 Gateway 
```
Para exibir o conteúdo de um arquivo chamado ipconfig. out – junto com as coordenadas correspondentes do conteúdo — em um computador chamado Computador1, digite:
```
setx /s computer1 /u maindom\hiropln /p p@ssW23 /f ipconfig.out /x 
```

#### <a name="additional-references"></a>Referências adicionais

[Chave da sintaxe de linha de comando](command-line-syntax-key.md)