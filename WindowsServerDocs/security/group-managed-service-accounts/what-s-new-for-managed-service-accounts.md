---
title: What's New for Managed Service Accounts
description: Segurança do Windows Server
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: security-gmsa
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2f2a8b6b-c152-4c40-b712-bfabff0e408b
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/12/2016
ms.openlocfilehash: de4d64e3dbe4bc7c7cba32f066a696636632224d
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71403728"
---
# <a name="what39s-new-for-managed-service-accounts"></a>O&#39;que há de novo para contas de serviço gerenciado

>Aplicável ao: Windows Server (canal semestral), Windows Server 2016

Este tópico para o profissional de ti descreve as alterações na funcionalidade de contas de serviço gerenciadas com a introdução da conta de serviço gerenciado de grupo (gMSA) no Windows Server 2012 e no Windows 8.

A conta de serviço gerenciado foi desenvolvida para fornecer serviços e tarefas, como serviços do Windows e pools de aplicativos do IIS, para compartilhar suas próprias contas de domínio, ao mesmo tempo em que elimina a necessidade de um administrador para administrar manualmente as senhas dessas contas. É uma conta de domínio gerenciado que oferece o gerenciamento automático de senha.

## <a name="versions"></a>O que há de novo para contas de serviço gerenciado no Windows Server 2012 e no Windows 8
O seguinte descreve quais alterações na funcionalidade foram feitas ao MSA no Windows Server 2012 e no Windows 8.

### <a name="group-managed-service-accounts"></a>Contas de serviço gerenciado de grupo
Quando uma conta de domínio está configurada para um servidor em um domínio, o computador cliente pode autenticar e conectar a esse serviço. Anteriormente, apenas dois tipos de conta forneciam identidade sem exigir o gerenciamento de senha. Porém, esses tipos de conta têm limitações:

-   A conta de computador é limitada a um servidor de domínio e as senhas são gerenciadas pelo computador.

-   A Conta de Serviço Gerenciado é limitada a um servidor de domínio e as senhas são gerenciadas pelo computador.

Essas contas não podem ser compartilhadas por vários sistemas. Portanto, você deve manter regularmente a conta de cada serviço em cada sistema para impedir a expiração indesejada da senha.

**Qual é o valor agregado desta alteração?**

A conta de serviço gerenciado de grupo resolve esse problema porque a senha da conta é gerenciada pelos controladores de domínio do Windows Server 2012 e pode ser recuperada por vários sistemas Windows Server 2012. Isso minimiza a sobrecarga administrativa de uma conta de serviço, permitindo que o Windows controle o gerenciamento de senha dessas contas.

**O que passou a funcionar de maneira diferente?**

Em computadores que executam o Windows Server 2012 ou o Windows 8, um grupo MSA pode ser criado e gerenciado por meio do Gerenciador de controle de serviço para que várias instâncias do serviço, como implantadas em um farm de servidores, possam ser gerenciadas de um servidor. Ferramentas e utilitários que você usava para administrar Contas de Serviço Gerenciado, como o Gerenciador de Pool de Aplicativos do IIS, podem ser usados com Contas de Serviço Gerenciado de grupo. Administradores de domínio podem delegar o gerenciamento de serviços a administradores de serviço, que por sua vez podem gerenciar todo o ciclo de vida de uma Conta de Serviços Gerenciados ou da Conta de Serviços Gerenciados de grupo. Os computadores cliente existentes poderão autenticar em qualquer serviço desse tipo sem saber em que instância de serviço estão autenticando.

### <a name="interoperability"></a>Funcionalidade removida ou preterida
Para o Windows Server 2012, os cmdlets do Windows PowerShell assumem como padrão o gerenciamento das contas de serviço gerenciado de grupo em vez das contas de serviço gerenciado do servidor.

## <a name="see-also"></a>Consulte também

-   [Visão geral de contas de serviço gerenciado de grupo](group-managed-service-accounts-overview.md)

-   [Visão geral do Active Directory Domain Services](active-directory-domain-services-overview.md)

-   [Contas de serviço gerenciado: Noções básicas, implementação, práticas recomendadas e solução de problemas](http://blogs.technet.com/b/askds/archive/20../managed-service-accounts-understanding-implementing-best-practices-and-troubleshooting.aspx)


