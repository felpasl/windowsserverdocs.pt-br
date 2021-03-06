---
title: Que tipo de instalação é ideal para você
description: Este tópico descreve as diferentes opções de instalação do centro de administração do Windows, incluindo a instalação do em um PC com Windows 10 ou um Windows Server para uso por vários administradores.
ms.technology: manage
ms.topic: article
author: nwashburn-ms
ms.author: niwashbu
ms.localizationpriority: medium
ms.prod: windows-server
ms.date: 12/02/2019
ms.openlocfilehash: d4046cc10a5e0fdc12cfb9587eef10d4263c2ddd
ms.sourcegitcommit: 7c7fc443ecd0a81bff6ed6dbeeaf4f24582ba339
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2019
ms.locfileid: "74904015"
---
# <a name="what-type-of-installation-is-right-for-you"></a>Que tipo de instalação é ideal para você?

Este tópico descreve as diferentes opções de instalação do centro de administração do Windows, incluindo a instalação do em um PC com Windows 10 ou um Windows Server para uso por vários administradores. Para instalar o centro de administração do Windows em uma VM no Azure, consulte [implantar o centro de administração do Windows no Azure](../azure/deploy-wac-in-azure.md).

## <a name="installation-types"></a>Instalação: tipos

![img](../media/deployment-options/install-options.PNG)

| Cliente local                                | Servidor Gateway                                  | Servidor gerenciado                               | Cluster de failover                           |
|---------------------------------------------|-------------------------------------------------|----------------------------------------------|--------------------------------------------|
| [Instale](../deploy/install.md) o em um cliente Windows 10 local que tenha conectividade com os servidores gerenciados.  Ótimo para cenários de início rápido, teste, ad hoc ou de pequena escala. |[Instale](../deploy/install.md) o em um servidor de gateway designado e acesse de qualquer navegador cliente com conectividade com o servidor de gateway.  Ótimo para cenários em grande escala. | [Instale](../deploy/install.md) diretamente em um servidor gerenciado com a finalidade de gerenciar a si mesmo ou um cluster no qual ele seja um nó de membro.  Ótimo para cenários distribuídos. | [Implante](#high-availability) em um cluster de failover para habilitar a alta disponibilidade do serviço de gateway. Ótimo para ambientes de produção para garantir a resiliência do seu serviço de gerenciamento. |

## <a name="installation-supported-operating-systems"></a>Instalação: sistemas operacionais com suporte

Você pode **instalar** o centro de administração do Windows nos seguintes sistemas operacionais Windows:

| **Plataforma**                       | **Modo de instalação** |
| -----------------------------------| --------------------- |
| Windows 10                         | Cliente local |
| Canal semestral do Windows Server | Servidores de gateway, servidor gerenciado, cluster de failover |
| Windows Server 2016                | Servidores de gateway, servidor gerenciado, cluster de failover |
| Windows Server 2019                | Servidores de gateway, servidor gerenciado, cluster de failover |

Para operar o centro de administração do Windows:

- **Em cenário de cliente local:** Inicie o gateway do centro de administração do Windows no menu iniciar e conecte-se a ele em um navegador da Web do cliente acessando `https://localhost:6516`.
- **Em outros cenários:** Conecte-se ao gateway do centro de administração do Windows em um computador diferente de um navegador cliente por meio de sua URL, por exemplo, `https://servername.contoso.com`

> [!WARNING]
> Não há suporte para a instalação do centro de administração do Windows em um controlador de domínio. [Leia mais sobre as práticas recomendadas de segurança do controlador de domínio](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/security-best-practices/securing-domain-controllers-against-attack).

## <a name="installation-supported-web-browsers"></a>Instalação: navegadores da Web com suporte

O Microsoft Edge (incluindo [o Microsoft Edge Insider](https://microsoftedgeinsider.com)) e o Google Chrome são testados e têm suporte no Windows 10. Outros navegadores da Web, incluindo o Internet Explorer e o Firefox, atualmente não fazem parte de nossa matriz de testes e, portanto, não têm suporte *oficialmente* . Esses navegadores podem ter problemas ao executar o centro de administração do Windows. Por exemplo, o Firefox tem seu próprio repositório de certificados, portanto, você deve importar o certificado de `Windows Admin Center Client` no Firefox para usar o centro de administração do Windows no Windows 10. Para obter mais detalhes, consulte [problemas conhecidos específicos do navegador](../support/known-issues.md#browser-specific-issues).

## <a name="management-target-supported-operating-systems"></a>Destino de gerenciamento: sistemas operacionais com suporte

Você pode **gerenciar** os seguintes sistemas operacionais Windows usando o centro de administração do Windows:

| Versão | Gerenciar *nó* via *Gerenciador do servidor* | Gerenciar por meio do *Gerenciador de cluster* |
| ------------------------- |--------------- | ----- |
| Windows 10 | Sim (por meio do gerenciamento do computador) | N/D |
| Canal semestral do Windows Server | Sim | Sim |
| Windows Server 2019 | Sim | Sim |
| Windows Server 2016 | Sim | Sim, com a [atualização cumulativa mais recente](../use/manage-hyper-converged.md#prepare-your-windows-server-2016-cluster-for-windows-admin-center) |
| Microsoft Hyper-V Server 2016 | Sim | Sim |
| Windows Server 2012 R2 | Sim | Sim |
| Microsoft Hyper-V Server 2012 R2 | Sim | Sim |
| Windows Server 2012 | Sim | Sim |
| Windows Server 2008 R2 | Sim, funcionalidade limitada | N/D |

> [!NOTE]
> O centro de administração do Windows requer recursos do PowerShell que não estão incluídos no Windows Server 2008 R2, 2012 e 2012 R2. Se você gerenciá-los com o centro de administração do Windows, será necessário instalar o Windows Management Framework (WMF) versão 5,1 ou superior nesses servidores.
> 
> Digite `$PSVersiontable` no PowerShell para verificar se o WMF está instalado e se a versão é 5.1 ou superior. 
> 
> Se o WMF não estiver instalado, você poderá [baixar o wmf 5,1](https://www.microsoft.com/en-us/download/details.aspx?id=54616).

## <a name="high-availability"></a>Alta disponibilidade

Você pode habilitar a alta disponibilidade do serviço de gateway implantando o centro de administração do Windows em um modelo ativo-passivo em um cluster de failover. Se um dos nós no cluster falhar, o centro de administração do Windows executará um failover normal para outro nó, permitindo que você continue gerenciando os servidores em seu ambiente sem problemas.

[Saiba como implantar o centro de administração do Windows com alta disponibilidade.](../deploy/high-availability.md)

> [!Tip]
> Pronto para instalar o Windows Admin Center? [Baixar agora](https://aka.ms/windowsadmincenter)
