---
title: Configuração de scwcmd
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6528b9dc-3d82-4228-b734-ed717458d74c
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 43bd70c33294b09f63b9718e4c0f2cdc6cace156
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71384292"
---
# <a name="scwcmd-configure"></a>Scwcmd: configure

> Aplica-se a: Windows Server 2012 R2, Windows Server 2012

Aplica uma política de segurança gerada pelo assistente de configuração de segurança (SCW) a um computador. Essa ferramenta de linha de comando também aceita uma lista de nomes de computador como entrada.

## <a name="syntax"></a>Sintaxe

```
scwcmd configure [[[/m:<ComputerName> | /ou:<OuName>] /p:<Policy>] | /i:<ComputerList>] [/u:<UserName>] [/pw:<Password>] [/t:<Threads>]
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|/m: \<ComputerName >|Especifica o nome NetBIOS, o nome DNS ou o endereço IP do computador a ser configurado. Se o parâmetro **/m** for especificado, o parâmetro **/p** também deverá ser especificado.|
|/ou: \<OuName >|Especifica o FQDN (nome de domínio totalmente qualificado) de uma UO (unidade organizacional) em Active Directory Domain Services. Se o parâmetro **/ou** for especificado, o parâmetro **/p** também deverá ser especificado. Todos os computadores da UO serão analisados de acordo com a política fornecida.|
|/p: \<Policy >|Especifica o caminho e o nome do arquivo de política. XML a ser usado para executar a configuração.|
|/i: \<ComputerList >|Especifica o caminho e o nome de arquivo de um arquivo. XML que contém uma lista de computadores junto com seus arquivos de política esperados. Todos os computadores no arquivo. XML serão configurados de acordo com seus arquivos de política correspondentes. Um arquivo. XML de exemplo é%windir%\security\SampleMachineList.xml.|
|/u: \<UserName >|Especifica uma credencial de usuário alternativa a ser usada ao configurar um computador remoto. O padrão é o usuário conectado.|
|/PW: \<Password >|Especifica uma credencial de usuário alternativa a ser usada ao configurar um computador remoto. O padrão é a senha do usuário conectado.|
|/t: \<Threads >|Especifica o número de operações de configuração pendentes simultâneas que devem ser mantidas durante o processo de configuração (DefaultValue = 40, MinValue = 1, MaxValue = 1000).|
|/?|Exibe a ajuda no prompt de comando.|

## <a name="remarks"></a>Comentários

Scwcmd. exe só está disponível em computadores que executam o Windows Server 2008 R2, o Windows Server 2008 ou o Windows Server 2003.

## <a name="BKMK_Examples"></a>Disso

Para configurar uma política de segurança no arquivo webpolicy. xml, digite:
```
scwcmd configure /p:webpolicy.xml
```
Para configurar uma política de segurança para o computador em 172.16.0.0 em relação ao arquivo webpolicy. xml usando as credenciais da conta WebAdmin, digite:
```
scwcmd configure /m:172.16.0.0 /p:webpolicy.xml /u:webadmin
```
Para configurar uma política de segurança em todos os computadores na lista campusmachines. XML com um máximo de 100 threads, digite:
```
scwcmd configure /i:campusmachines.xml /t:100
```
Para configurar uma política de segurança em todos os computadores na UO de servidores WebServer no arquivo webpolicy. xml usando as credenciais da conta DomainAdmin, digite:
```
scwcmd configure /ou:OU=WebServers,DC=Marketing,DC=ABCCompany,DC=com /p:webpolicy.xml /u:DomainAdmin
```

#### <a name="additional-references"></a>Referências adicionais

-   [Chave da sintaxe de linha de comando](command-line-syntax-key.md)