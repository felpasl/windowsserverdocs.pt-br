---
ms.assetid: bbb5b68f-00ad-4715-8176-0c2769b706c4
title: Guia de Implantação do AD FS do Windows Server 2012 R2
description: ''
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server
ms.technology: identity-adfs
ms.openlocfilehash: e5507cd567114d17c6500655ee210b70bd9ea1ec
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71408410"
---
# <a name="deploying-a-federation-server-farm"></a>Implantando um farm de servidores de federação


Para implantar um farm de servidores de federação, conclua as tarefas desta lista de verificação na ordem. Quando houver um link de referência para um tópico conceitual, retorne a esta lista de verificação depois de analisar o tópico conceitual, para realizar as tarefas restantes da lista de verificação.  
  
Lista de verificação de ![implantação do farm de servidores federados](media/2b05dce3-938f-4168-9b8f-1f4398cbdb9b.gif)**: Implantando um farm de servidores de Federação**  
  
||Tarefa|Referência|  
|-|--------|-------------|  
|![Implantando farm de servidores federados](media/icon_checkboxo.gif)|Examine os conceitos e considerações importantes ao se preparar para implantar Serviços de Federação do Active Directory (AD FS) \(AD FS\). **Observação:**|![implantando o farm](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[de servidores federados AD FS guia de design no Windows server 2012 R2](../../ad-fs/design/AD-FS-Design-Guide-in-Windows-Server-2012-R2.md)<br /><br />![implantando o farm de servidores federados](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[entendendo os principais conceitos de AD FS](../../ad-fs/technical-reference/Understanding-Key-AD-FS-Concepts.md)|  
||Se você decidir usar o Microsoft SQL Server como repositório de configuração do AD FS, certifique-se de implantar uma instância funcional do SQL Server.|Aviso de [SQL Server](https://technet.microsoft.com/sqlserver) **:** no Windows Server 2012 R2, se você quiser criar um farm de AD FS e usar SQL Server para armazenar seus dados de configuração, poderá usar SQL Server 2008 e versões mais recentes, incluindo SQL Server 2012.|  
|![Implantando farm de servidores federados](media/icon_checkboxo.gif)|Una seu computador a um domínio do Active Directory.|![implantar o farm de servidores federados](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[ingressar um computador em um domínio](Join-a-Computer-to-a-Domain.md)|  
|![Implantando farm de servidores federados](media/icon_checkboxo.gif)|Registre uma camada de soquete seguro \(SSL\) certificado para AD FS.|![implantando o farm](media/bc6cea1a-1c6c-4124-8c8f-1df5adfe8c88.gif)[de servidores federados registrar um certificado SSL para AD FS](Enroll-an-SSL-Certificate-for-AD-FS.md)|  
|![Implantando farm de servidores federados](media/icon_checkboxo.gif)|Instale o serviço de função do AD FS.|![implantar o farm de servidores federados](media/bc6cea1a-1c6c-4124-8c8f-1df5adfe8c88.gif)[instalar o serviço de função de AD FS](Install-the-AD-FS-Role-Service.md)|  
|![Implantando farm de servidores federados](media/icon_checkboxo.gif)|Configure um servidor de federação.|![implantando o farm](media/bc6cea1a-1c6c-4124-8c8f-1df5adfe8c88.gif)[de servidores federados configurar um servidor de Federação](Configure-a-Federation-Server.md)|  
|![Implantando farm de servidores federados](media/icon_checkboxo.gif)|Etapa opcional: Configure um servidor de Federação com o serviço de registro de dispositivo \(DRS\).|![implantando o farm](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[de servidores federados configurar um servidor de Federação com o serviço de registro de dispositivo](Configure-a-federation-server-with-Device-Registration-Service.md)|  
|![Implantando farm de servidores federados](media/icon_checkboxo.gif)|Adicione um host \(um\) e alias \(registro de recurso CNAME\) ao sistema de nomes de domínio corporativo \(DNS\) para o serviço de Federação e o DRS.|![implantar o farm de servidores federados](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Configurar o DNS corporativo para o serviço de Federação e o DRS](Configure-Corporate-DNS-for-the-Federation-Service-and-DRS.md)|  
|![Implantando farm de servidores federados](media/icon_checkboxo.gif)|Verificar se um servidor de federação está operacional.|![implantar o farm de servidores federados](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Verifique se um servidor de Federação está operacional](Verify-That-a-Federation-Server-Is-Operational.md)|  
  

## <a name="see-also"></a>Consulte também  
[Implantação do AD FS](../../ad-fs/AD-FS-Deployment.md)  

[Guia de implantação do Windows Server 2012 R2 AD FS](../../ad-fs/deployment/Windows-Server-2012-R2-AD-FS-Deployment-Guide.md)  
  

