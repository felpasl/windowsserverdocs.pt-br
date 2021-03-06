---
title: Autenticação de chave pública de dispositivo ingressado no domínio
ms.custom: na
ms.prod: windows-server
ms.topic: article
ms.assetid: 7bd17803-6e42-4a3b-803f-e47c74725813
manager: alanth
author: michikos
ms.technology: security-authentication
ms.date: 08/18/2017
ms.openlocfilehash: 616ebf1a8e01f84618d22d535609a0dc8414d718
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71403494"
---
# <a name="domain-joined-device-public-key-authentication"></a>Autenticação de chave pública de dispositivo ingressado no domínio

>Aplica-se a: Windows Server 2016, Windows 10

O Kerberos adicionou suporte para dispositivos ingressados no domínio para entrar usando um certificado que começa com o Windows Server 2012 e o Windows 8. Essa alteração permite que fornecedores de terceiros criem soluções para provisionar e inicializar certificados para dispositivos ingressados no domínio a serem usados para autenticação de domínio. 

## <a name="automatic-public-key-provisioning"></a>Provisionamento automático de chave pública

A partir do Windows 10 versão 1507 e do Windows Server 2016, os dispositivos ingressados no domínio provisionam automaticamente uma chave pública associada a um controlador de domínio do Windows Server 2016 (DC). Depois que uma chave é provisionada, o Windows pode usar a autenticação de chave pública para o domínio.

### <a name="public-key-generation"></a>Geração de chave pública
Se o dispositivo estiver executando o Credential Guard, uma chave pública será criada protegida pelo Credential Guard. 

Se o Credential Guard não estiver disponível e um TPM for, uma chave pública será criada protegida pelo TPM. 

Se nenhum estiver disponível, uma chave não será gerada e o dispositivo só poderá ser autenticado usando a senha.

### <a name="provisioning-computer-account-public-key"></a>Provisionando chave pública de conta de computador
Quando o Windows é iniciado, ele verifica se uma chave pública é provisionada para sua conta de computador. Caso contrário, ele gera uma chave pública vinculada e a configura para sua conta no AD usando um controlador de domínio do Windows Server 2016 ou superior. Se todos os DCs estiverem no nível inferior, nenhuma chave será provisionada.

### <a name="configuring-device-to-only-use-public-key"></a>Configurando o dispositivo para usar apenas a chave pública
Se a configuração de Política de Grupo **suporte para autenticação de dispositivo usando o certificado** estiver definida como **forçar**, o dispositivo precisará localizar um controlador de domínio que execute o Windows Server 2016 ou posterior para autenticar. A configuração está em Modelos Administrativos Sistema > > Kerberos.

### <a name="configuring-device-to-only-use-password"></a>Configurando o dispositivo para usar apenas a senha
Se a configuração de Política de Grupo **suporte para autenticação de dispositivo usando o certificado** estiver desabilitada, a senha sempre será usada. A configuração está em Modelos Administrativos Sistema > > Kerberos.

## <a name="domain-joined-device-authentication-using-public-key"></a>Autenticação de dispositivo ingressado no domínio usando a chave pública
Quando o Windows tem um certificado para o dispositivo ingressado no domínio, o Kerberos primeiro se autentica usando o certificado e, em caso de falha, tenta novamente com a senha. Isso permite que o dispositivo se autentique em DCs de nível inferior.

Como as chaves públicas provisionadas automaticamente têm um certificado autoassinado, a validação de certificado falha em controladores de domínio que não dão suporte ao mapeamento de conta de confiança de chave. Por padrão, o Windows tenta a autenticação novamente usando a senha de domínio do dispositivo.


