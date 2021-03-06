---
title: bitsadmin setclientcertificatebyid
description: O tópico de comandos do Windows para **Bitsadmin setclientcertificatebyid** especifica o identificador do certificado do cliente a ser usado para autenticação de cliente em uma solicitação HTTPS (SSL)
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8585a7a1-7472-437b-b04a-a11925782a3a
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 53b6fa4c65397cf710d0497fbae889afd31ec136
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71380733"
---
# <a name="bitsadmin-setclientcertificatebyid"></a>bitsadmin setclientcertificatebyid



Especifica o identificador do certificado do cliente a ser usado para autenticação de cliente em uma solicitação HTTPS (SSL).

## <a name="syntax"></a>Sintaxe

```
bitsadmin /SetClientCertificateByID <Job> <store_location> <store_name> hexa-decimal_cert_id>
```

## <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|Job|O nome de exibição ou o GUID do trabalho|
|Store_location|Identifica o local de um armazenamento do sistema a ser usado para pesquisar o certificado. Os valores possíveis incluem:</br>1 (CURRENT_USER)</br>2 (LOCAL_MACHINE)</br>3 (CURRENT_SERVICE)</br>4 (SERVIÇOS)</br>5 (USUÁRIOS)</br>6 (CURRENT_USER_GROUP_POLICY)</br>7 (LOCAL_MACHINE_GROUP_POLICY)</br>8 (LOCAL_MACHINE_ENTERPRISE)|
|Store_name|O nome do repositório de certificados. Os valores possíveis incluem:</br>AC (certificados de autoridade de certificação)</br>MEU (certificados pessoais)</br>RAIZ (certificados raiz)</br>SPC (certificado do fornecedor de software)|
|Hexadecimal_cert_id|Um número hexadecimal que representa o hash do certificado|

## <a name="BKMK_examples"></a>Disso

O exemplo a seguir especifica o identificador do certificado do cliente a ser usado para autenticação de cliente em uma solicitação HTTPS (SSL) para o trabalho chamado *myJob*.
```
C:\>bitsadmin Bitsadmin /SetClientCertificateByID myJob BG_CERT_STORE_LOCATION_CURRENT_USER MY A106B52356D3FBCD1853A41B619358BD 
```

#### <a name="additional-references"></a>Referências adicionais

[Chave da sintaxe de linha de comando](command-line-syntax-key.md)