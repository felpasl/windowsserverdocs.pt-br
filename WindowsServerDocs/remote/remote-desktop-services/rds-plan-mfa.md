---
title: Serviços de Área de Trabalho Remota – Autenticação Multifator
description: Informações de planejamento para usar a MFA com RDS.
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: remote-desktop-services
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 09ea784e-5644-417a-a3d9-bdbcebc313f9
author: lizap
ms.author: elizapo
ms.date: 09/07/2016
manager: dongill
ms.openlocfilehash: 833eafd0b762098b67b11e6e5f26f63e62057fd1
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71403850"
---
# <a name="remote-desktop-services---multi-factor-authentication"></a>Serviços de Área de Trabalho Remota – Autenticação Multifator

>Aplica-se a: Windows Server (Canal Semestral), Windows Server 2019, Windows Server 2016

Aproveite o poder do Active Directory com a Autenticação Multifator para aplicar a proteção de alta segurança a seus recursos de negócios.

Para os usuários finais que se conectam a suas áreas de trabalho e aplicativos, a experiência é semelhante à que eles já têm, pois eles realizam uma segunda etapa de autenticação para se conectarem ao recurso desejado:
- Iniciar uma área de trabalho ou RemoteApp de um arquivo RDP ou por meio de um aplicativo de cliente de área de trabalho remota
- Após a conexão com o gateway de área de trabalho remota para acesso remoto seguro, receba um SMS ou um desafio de MFA no aplicativo móvel
- Autentique corretamente e conecte-se aos seus recursos.

Para obter mais detalhes sobre o processo de configuração, confira [Integrar a infraestrutura do gateway de área de trabalho remota usando a extensão de NPS (Servidor de Políticas de Rede) e o Azure AD](https://docs.microsoft.com/azure/multi-factor-authentication/nps-extension-remote-desktop-gateway).
