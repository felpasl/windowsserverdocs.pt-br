---
ms.assetid: f7f6bac2-1100-4b00-a248-4ca3eb3cdbe9
title: Alterando o logotipo da empresa na página de entrada AD FS
description: ''
author: billmath
ms.author: billmath
manager: femila
ms.date: 03/08/2017
ms.topic: article
ms.prod: windows-server
ms.technology: identity-adfs
ms.openlocfilehash: b22c969e0113081e1ca8a662ae81a2ee24829835
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71358299"
---
# <a name="changing-the-company-logo-on-the-ad-fs-sign-in-page"></a>Alterando o logotipo da empresa na página de entrada AD FS

#### <a name="change-company-logo"></a>Altere o logotipo da empresa  
Para alterar o logotipo da empresa exibido na página\-de entrada, use o cmdlet e a sintaxe do PowerShell do Windows PowerShell a seguir.  

![alterar logotipo](media/AD-FS-user-sign-in-customization/ADFS_Blue_Custom2.png)
  
> [!IMPORTANT]  
> Recomendamos que as dimensões para o logotipo sejam de 260x35 a 96 DPI com um arquivo que não exceda o tamanho de 10 KB.  
  
    
    Set-AdfsWebTheme -TargetName default -Logo @{path="c:\Contoso\logo.png"}  

  
> [!NOTE]  
> O parâmetro `TargetName` é necessário. O tema padrão que é liberado com AD FS é denominado *padrão*.  

## <a name="additional-references"></a>Referências adicionais 
[AD FS a personalização de entrada do usuário](AD-FS-user-sign-in-customization.md)  
