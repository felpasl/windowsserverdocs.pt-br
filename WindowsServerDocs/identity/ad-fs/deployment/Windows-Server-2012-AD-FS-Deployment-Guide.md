---
ms.assetid: e2ad9e80-a036-4bac-a4fb-afa83756aa1f
title: Guia de Implantação do AD FS do Windows Server 2012
description: ''
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server
ms.technology: identity-adfs
ms.openlocfilehash: 1597230fcfde4fe8a9767f0f14c634bc6fabdceb
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71408251"
---
# <a name="windows-server-2012-ad-fs-deployment-guide"></a>Guia de Implantação do AD FS do Windows Server 2012


Você pode usar Active Directory® serviços \(de Federação AD FS\) com o sistema operacional Windows Server® 2012 para criar uma solução de gerenciamento de identidade federada que estenda a identificação distribuída, a autenticação e serviços de autorização para\-aplicativos baseados na Web em limites de plataforma e organização. Ao implantar AD FS, você pode estender os recursos de gerenciamento de identidade existentes da sua organização para a Internet.  
  
Você pode implantar o AD FS para:  
  
-   Forneça aos seus funcionários ou clientes uma experiência\-de \(SSO\) de\-logon\-único com base na Web quando eles precisarem de acesso remoto a sites ou serviços hospedados internamente.  
  
-   Forneça aos seus funcionários ou clientes uma experiência\-de SSO baseada na Web quando eles acessarem sites ou serviços da organização cruzada\-de dentro dos firewalls da sua rede.  
  
-   Forneça aos seus funcionários ou clientes acesso contínuo a recursos\-baseados na Web em qualquer organização de parceiro de Federação na Internet sem exigir que os funcionários ou clientes façam logon mais de uma vez.  
  
-   Mantenha o controle completo sobre suas identidades de funcionário ou cliente sem\-usar outros \(provedores de logon do Windows Live ID, do\)Liberty Alliance e outros.  
  
## <a name="about-this-guide"></a>Sobre este guia  
Este guia destina-se para uso por administradores e engenheiros de sistema. Ele fornece diretrizes detalhadas para a implantação de um design de AD FS que foi previamente selecionado por você ou por um especialista em infraestrutura ou arquiteto de sistema em sua organização.  
  
Se um design ainda não tiver sido selecionado, recomendamos que você aguarde para seguir as instruções neste guia até ter revisado as opções de design no [Guia de design de AD FS no Windows Server 2012](https://technet.microsoft.com/library/dd807036.aspx) e tiver selecionado o design mais apropriado para seu organizações. Para obter mais informações sobre como usar este guia com um design que já foi selecionado, consulte [implementando seu plano de design de AD FS](Implementing-Your-AD-FS-Design-Plan.md).  
  
Depois de selecionar o design no guia de design e reunir as informações necessárias sobre declarações, tipos de token, repositórios de atributos e outros itens, você pode usar este guia para implantar seu design de AD FS em seu ambiente de produção. Este guia fornece as etapas para implantar um dos seguintes designs de AD FS primários:  
  
-   SSO da Web  
  
-   SSO da Web federado  
  
Use as listas de verificação em [implementando seu plano de design de AD FS](Implementing-Your-AD-FS-Design-Plan.md) para determinar a melhor maneira de usar as instruções neste guia para implantar seu design específico. Para obter informações sobre os requisitos de hardware e software para a implantação de [AD FS, consulte o apêndice a: Revisando](https://technet.microsoft.com/library/ff678034.aspx) os requisitos de AD FS no guia de design de AD FS.  
  
### <a name="what-this-guide-does-not-provide"></a>O que este guia não contém  
O que este guia não contém:  
  
-   Orientação sobre quando e onde posicionar servidores de Federação, proxies de servidor de Federação ou servidores Web em sua infraestrutura de rede existente. Para obter essas informações, consulte planejando o posicionamento do [servidor de Federação](https://technet.microsoft.com/library/dd807069.aspx) e planejando o posicionamento do proxy do servidor de [Federação](https://technet.microsoft.com/library/dd807130.aspx) no guia de design do AD FS.  
  
-   Diretrizes para usar CAS \(\) de autoridades de certificação para configurar AD FS  
  
-   Diretrizes para configurar ou configurar aplicativos específicos baseados\-na Web  
  
-   Instruções de configuração específicas para configurar um ambiente de laboratório de teste.  
  
-   Informações sobre como personalizar telas de logon federadas, arquivos web.config ou o banco de dados de configuração.  
  
## <a name="in-this-guide"></a>Neste guia  
  
-   [Como planejar a implantação do AD FS](Planning-to-Deploy-AD-FS.md)  
  
-   [Como implementar seu plano de design do AD FS](Implementing-Your-AD-FS-Design-Plan.md)  
  
-   [Lista de verificação: Como implementar um design SSO da Web](Checklist--Implementing-a-Web-SSO-Design.md)  
  
-   [Lista de verificação: Como implementar um design de SSO da Web federado](Checklist--Implementing-a-Federated-Web-SSO-Design.md)  
  
-   [Configurando organizações parceiras](Configuring-Partner-Organizations.md)  
  
-   [Como configurar regras de declaração](Configuring-Claim-Rules.md)  
  
-   [Como implantar servidores de federação](Deploying-Federation-Servers.md)  
  
-   [Como implantar proxies de servidor de federação](Deploying-Federation-Server-Proxies.md)  
  
-   [Como interoperar com o AD FS 1.x](Interoperating-with-AD-FS-1.x.md)  
