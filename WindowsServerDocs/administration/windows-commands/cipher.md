---
title: cipher
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 78ef795e-0f87-4acd-8d15-192c972c0f41
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 7ba6a54c275e1765bfdc31fe30d78fc6e3da6c05
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71379360"
---
# <a name="cipher"></a>cipher



Exibe ou altera a criptografia de diretórios e pastas em volumes NTFS. Se usado sem parâmetros, **Cipher** exibe o estado de criptografia do diretório atual e os arquivos que ele contém.

Para obter exemplos de como usar esse comando, consulte [Exemplos](#BKMK_examples).

## <a name="syntax"></a>Sintaxe

```
cipher [/e | /d | /c] [/s:<Directory>] [/b] [/h] [PathName [...]]
cipher /k
cipher /r:<FileName> [/smartcard]
cipher /u [/n]
cipher /w:<Directory>
cipher /x[:efsfile] [FileName]
cipher /y
cipher /adduser [/certhash:<Hash> | /certfile:<FileName>] [/s:Directory] [/b] [/h] [PathName [...]]
cipher /removeuser /certhash:<Hash> [/s:<Directory>] [/b] [/h] [<PathName> [...]]
cipher /rekey [PathName [...]]
```

## <a name="parameters"></a>Parâmetros

|          Parâmetros           |                                                                                                                                                   Descrição                                                                                                                                                    |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              /b.               |                                                                                                    Anula se um erro for encontrado. Por padrão, a **codificação** continua a ser executada mesmo se forem encontrados erros.                                                                                                    |
|              /c               |                                                                                                                                   Exibe informações sobre o arquivo criptografado.                                                                                                                                    |
|              /d               |                                                                                                                                   Descriptografa os arquivos ou diretórios especificados.                                                                                                                                   |
|              /e               |                                                                                          Criptografa os arquivos ou diretórios especificados. Os diretórios são marcados de modo que os arquivos adicionados posteriormente serão criptografados.                                                                                           |
|              /h               |                                                                                                     Exibe arquivos com atributos ocultos ou de sistema. Por padrão, esses arquivos não são criptografados ou descriptografados.                                                                                                     |
|              /k               |                                                                            Cria um novo certificado e chave para uso com arquivos de Encrypting File System (EFS). Se o parâmetro **/k** for especificado, todos os outros parâmetros serão ignorados.                                                                            |
|  /r: \<FileName > [/SmartCard]  |   Gera uma chave e um certificado do agente de recuperação do EFS, em seguida, grava-os em um arquivo. pfx (que contém o certificado e a chave privada) e um arquivo. cer (que contém apenas o certificado). Se **/SmartCard** for especificado, ele gravará a chave de recuperação e o certificado em um cartão inteligente, e nenhum arquivo. pfx será gerado.   |
|        /s: \<Directory >        |                                                                                                               Executa a operação especificada em todos os subdiretórios no *diretório*especificado.                                                                                                               |
|            /u [/n]            |  Localiza todos os arquivos criptografados nas unidades locais. Se usado com o parâmetro **/n** , nenhuma atualização é feita. Se usado sem **/n**, **/u** compara a chave de criptografia de arquivo do usuário ou a chave do agente de recuperação com as atuais e as atualiza se elas foram alteradas. Esse parâmetro funciona apenas com **/n**.  |
|        /w: \<Directory >        | Remove dados do espaço em disco não utilizado disponível em todo o volume. Se você usar o parâmetro **/w** , todos os outros parâmetros serão ignorados. O diretório especificado pode estar localizado em qualquer lugar em um volume local. Se for um ponto de montagem ou apontar para um diretório em outro volume, os dados nesse volume serão removidos. |
|  /x [: efsfile] [\<FileName >]   |                                 Faz backup do certificado e das chaves do EFS para o nome de arquivo especificado. Se usado com **: efsfile**, **/x** faz backup dos certificados do usuário que foram usados para criptografar o arquivo. Caso contrário, será feito backup do certificado e das chaves atuais do EFS do usuário.                                 |
|              /y               |                                                                                                                      Exibe a miniatura do certificado EFS atual no computador local.                                                                                                                      |
|  /adduser [/certhash: \<Hash de >  |                                                                                                                                              /CertFile: <FileName>]                                                                                                                                               |
|            /rekey             |                                                                                                                 Atualiza os arquivos criptografados especificados para usar a chave EFS configurada atualmente.                                                                                                                 |
| /RemoveUser/certhash: \<Hash > |                                                                                       Remove um usuário dos arquivos especificados. O *hash* fornecido para **/certhash** deve ser o hash SHA1 do certificado a ser removido.                                                                                       |
|              /?               |                                                                                                                                       Exibe a ajuda no prompt de comando.                                                                                                                                       |

## <a name="remarks"></a>Comentários

-   Se o diretório pai não estiver criptografado, um arquivo criptografado poderá ser descriptografado quando for modificado. Portanto, ao criptografar um arquivo, você também deve criptografar o diretório pai.
-   Um administrador pode adicionar o conteúdo de um arquivo. cer à política de recuperação EFS para criar o agente de recuperação para usuários e, em seguida, importar o arquivo. pfx para recuperar arquivos individuais.
-   Você pode usar vários nomes de diretório e curingas.
-   Você deve colocar espaços entre vários parâmetros.

## <a name="BKMK_examples"></a>Disso

Para exibir o status de criptografia de cada um dos arquivos e subdiretórios no diretório atual, digite:
```
cipher
```
Os diretórios e arquivos criptografados são marcados com um **e**. Os arquivos e diretórios não criptografados são marcados com um **U**. Por exemplo, a saída a seguir indica que o diretório atual e todo o seu conteúdo não está criptografado no momento:
```
Listing C:\Users\MainUser\Documents\
New files added to this directory will not be encrypted.
U Private
U hello.doc
U hello.txt
```
Para habilitar a criptografia no diretório particular usado no exemplo anterior, digite:
```
cipher /e private
```
A saída a seguir exibe:
```
Encrypting files in C:\Users\MainUser\Documents\
Private             [OK]
1 file(s) [or directorie(s)] within 1 directorie(s) were encrypted.
```
O comando **Cipher** exibe a seguinte saída:
```
Listing C:\Users\MainUser\Documents\
New files added to this directory will not be encrypted.
E Private
U hello.doc
U hello.txt
```
Observe que o diretório particular está marcado como criptografado.

#### <a name="additional-references"></a>Referências adicionais

[Chave da sintaxe de linha de comando](command-line-syntax-key.md)