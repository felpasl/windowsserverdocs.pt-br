---
title: Etapa 2 configurar o servidor RADIUS
description: Este tópico faz parte do guia implantar o acesso remoto com autenticação OTP no Windows Server 2016.
manager: brianlic
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: networking-ras
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0326818f-9144-496c-b946-f82be4eefbd3
ms.author: pashort
author: shortpatti
ms.openlocfilehash: 00ea76d6995f875e509a3bc9ef0bab3d2689c52b
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71367023"
---
# <a name="step-2-configure-the-radius-server"></a>Etapa 2 configurar o servidor RADIUS

>Aplicável ao: Windows Server (canal semestral), Windows Server 2016

Antes de configurar o servidor de acesso remoto para dar suporte ao DirectAccess com suporte a OTP, configure o servidor RADIUS.  
  
|Tarefa|Descrição|  
|----|--------|  
|[2,1. configurar os tokens de distribuição de software RADIUS](#BKMK_1.1)|No servidor RADIUS, configure os tokens de distribuição de software.|  
|[2,2. configurar as informações de segurança do RADIUS](#BKMK_1.2)|No servidor RADIUS, configure as portas e o segredo compartilhado a serem usados.|  
|[2,3 adicionando conta de usuário para investigação de OTP](#BKMK_Probe)|No servidor RADIUS, crie uma nova conta de usuário para investigação de OTP.|  
|[2,4 sincronizar com Active Directory](#BKMK_Active)|No servidor RADIUS, crie contas de usuário sincronizadas com contas de Active Directory.|  
|[2,5 configurar o agente de autenticação RADIUS](#BKMK_AuthAgent)|Configure o servidor de acesso remoto como um agente de autenticação RADIUS.|  
  
## <a name="BKMK_1.1"></a>2,1 configurar os tokens de distribuição de software RADIUS  
O servidor RADIUS deve ser configurado com os tokens de licença e software e/ou de distribuição de hardware necessários a serem usados pelo DirectAccess com OTP. Esse processo será específico para cada implementação de fornecedor RADIUS.  
  
## <a name="BKMK_1.2"></a>2,2 configurar as informações de segurança do RADIUS  
O servidor RADIUS usa portas UDP para fins de comunicação, e cada fornecedor RADIUS tem suas próprias portas UDP padrão para comunicação de entrada e saída. Para que o servidor RADIUS funcione com o servidor de acesso remoto, verifique se todos os firewalls no ambiente estão configurados para permitir o tráfego UDP entre os servidores do DirectAccess e de OTP nas portas necessárias, conforme necessário.  
  
O servidor RADIUS usa um segredo compartilhado para fins de autenticação. Configure o servidor RADIUS com uma senha forte para o segredo compartilhado e observe que isso será usado ao configurar a configuração do computador cliente do servidor DirectAccess para uso com o DirectAccess com OTP.  
  
## <a name="BKMK_Probe"></a>2,3 adicionando conta de usuário para investigação de OTP  
No servidor RADIUS, crie uma nova conta de usuário chamada **DAProbeUser** e dê a ela a senha **DAProbePass**.  
  
## <a name="BKMK_Active"></a>2,4 sincronizar com Active Directory  
O servidor RADIUS deve ter contas de usuário que correspondam aos usuários no Active Directory que usará o DirectAccess com OTP.  
  
#### <a name="to-synchronize-the-radius-and-active-directory-users"></a>Para sincronizar os usuários RADIUS e Active Directory  
  
1.  Registre as informações do usuário de Active Directory para todos os DirectAccess com usuários de OTP.  
  
2.  Use o procedimento específico do fornecedor para criar contas de **domínio \ nome** de usuário idênticas no servidor RADIUS que foram registradas.  
  
## <a name="BKMK_AuthAgent"></a>2,5 configurar o agente de autenticação RADIUS  
O servidor de acesso remoto deve ser configurado como um agente de autenticação RADIUS para o DirectAccess com a implementação de OTP. Siga as instruções do fornecedor RADIUS para configurar o servidor de acesso remoto como um agente de autenticação RADIUS.  
  


