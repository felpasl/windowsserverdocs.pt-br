---
title: 'ksetup: addrealmflags'
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 80ca1e16-8871-494b-b9be-6bc9d63de860
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 543fcb8105d21020cc9a4ab5e5e8c1eca14a358b
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71375173"
---
# <a name="ksetupaddrealmflags"></a>ksetup: addrealmflags



Adiciona sinalizadores de realm adicionais ao realm especificado. Para obter exemplos de como esse comando pode ser usado, consulte [exemplos](#BKMK_Examples).

## <a name="syntax"></a>Sintaxe

```
ksetup /addrealmflags <RealmName> [sendaddress] [tcpsupported] [delegate] [ncsupported] [rc4]
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|Nome do Realm|O nome do realm é declarado como um nome DNS em maiúsculas, como CORP. CONTOSO.COM.|

## <a name="remarks"></a>Comentários

Os sinalizadores de realm especificam recursos adicionais de um realm Kerberos que não é baseado no sistema operacional Windows Server. Computadores que executam o Windows Server 2003, Windows Server 2008 ou Windows Server 2008 R2 podem usar um servidor Kerberos para administrar a autenticação em vez de usar um domínio que esteja executando um sistema operacional Windows Server, e esses sistemas participam de um Realm Kerberos. Essa entrada estabelece os recursos do realm. A tabela a seguir descreve cada um.

|Valor|Sinalizador de realm|Descrição|
|-----|----------|-----------|
|0xF|Todas|Todos os sinalizadores de realm estão definidos.|
|0x00|Nenhuma|Nenhum sinalizador de realm definido, e nenhum recurso adicional está habilitado.|
|0x01|SendAddress|O endereço IP será incluído dentro dos tíquetes de concessão de tíquetes.|
|0x02|TcpSupported|Tanto o protocolo TCP quanto o UDP (User Datagram Protocol) têm suporte nesse realm.|
|0x04|Delegar|Todos nesse realm são confiáveis para delegação.|
|0x08|NcSupported|Esse Realm dá suporte à canonização de nome, que permite padrões de nomenclatura de DNS e de realm.|
|0x80|RC4|Esse Realm dá suporte à criptografia RC4 para habilitar a relação de confiança entre territórios, o que permite o uso de TLS.|

Os sinalizadores de realm são armazenados no registro em **HKEY_LOCAL_MACHINE \system\currentcontrolset\control\lsa\kerberos\domains\\** <em>território-nome</em>. Essa entrada não existe no Registro por padrão. Você pode usar o comando [Ksetup: addrealmflags](ksetup-addrealmflags.md) para popular o registro.

Você pode ver quais sinalizadores de realm estão disponíveis e definidos exibindo a saída de ksetup ou ksetup/dumpstate.

## <a name="BKMK_Examples"></a>Disso

Lista os sinalizadores de realm disponíveis para o realm CONTOSO:
```
Ksetup /listrealmflags
```
Defina dois sinalizadores para o realm da CONTOSO:
```
ksetup /setrealmflags CONTOSO ncsupported delegate
```
Adicione mais um sinalizador que não esteja atualmente no conjunto:
```
ksetup /addrealmflags CONTOSO SendAddress
```
Execute o comando **ksetup** para verificar se o sinalizador de realm está definido exibindo a saída e procurando por **sinalizadores de realm =** .

#### <a name="additional-references"></a>Referências adicionais

-   [Ksetup:listrealmflags](ksetup-listrealmflags.md)
-   [Ksetup:setrealmflags](ksetup-setrealmflags.md)
-   [Ksetup:delrealmflags](ksetup-delrealmflags.md)
-   [Chave da sintaxe de linha de comando](command-line-syntax-key.md)