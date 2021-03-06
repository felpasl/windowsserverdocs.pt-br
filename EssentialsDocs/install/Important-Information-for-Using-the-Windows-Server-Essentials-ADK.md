---
title: Informações importantes para a utilização do Windows Server Essentials ADK
description: Descreve como usar o Windows Server Essentials
ms.custom: na
ms.date: 10/03/2016
ms.prod: windows-server-2016-essentials
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 26cb2992-1250-4672-98ee-8b870baa45d5
author: nnamuhcs
ms.author: coreyp
manager: dongill
ms.openlocfilehash: 4dec1fdf01538ca119b991675f932d2d8ec1e097
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59838637"
---
# <a name="important-information-for-using-the-windows-server-essentials-adk"></a>Informações importantes para a utilização do Windows Server Essentials ADK

>Aplica-se a: Windows Server 2016 Essentials, Windows Server 2012 R2 Essentials, Windows Server 2012 Essentials

Para criar e personalizar uma imagem do Windows Server Essentials, você usa muitas das ferramentas do [Windows 8 ADK](https://go.microsoft.com/fwlink/?LinkId=248647), mas há algumas diferenças importantes entre o Windows 8 ADK e o Windows Server Essentials ADK.  
  
 Você deve estar ciente das seguintes diferenças importantes:  
  
-   Algumas configurações foram alteradas em  **%windir%\setup\script\SetupComplete.cmd**. Se desejar usar esse comando, pode incluir linhas de comando adicionais, mas não remover as linhas existentes.  
  
## <a name="working-with-passwords"></a>Trabalhando com senhas  
  
-   A senha do administrador é definida como Admin@123 e logon automático está habilitado no Install.wim\unattend.XML. Portanto, não é preciso redigitar a senha várias vezes durante a configuração inicial do servidor. Se você tiver um unattend.xml personalizado na raiz da mídia removível, essas configurações serão substituídas e você precisará definir a senha e o logon durante a inicialização.  
  
-   Durante a Configuração Inicial, o usuário final é solicitado a criar uma nova conta e senha. Essa nova conta se torna a conta de administrador de rede para o sistema operacional. A conta de Administrador e o logon automático então são desabilitados. Você poderá automatizar esse processo usando o arquivo cfg.ini para testar a garantia de qualidade.  
  
-   Consulte a documentação do [Windows 8 ADK](https://go.microsoft.com/fwlink/?LinkId=248694) para obter detalhes sobre a criação de um arquivo unattend.xml.  
  
## <a name="see-also"></a>Consulte também  

 [Introdução ao Windows Server Essentials ADK](Getting-Started-with-the-Windows-Server-Essentials-ADK.md)   
 [Criando e personalizando a imagem](Creating-and-Customizing-the-Image.md)   
 [Personalizações adicionais](Additional-Customizations.md)   
 [Preparando a imagem para implantação](Preparing-the-Image-for-Deployment.md)   
 [Testando a experiência do usuário](Testing-the-Customer-Experience.md)

 [Introdução ao Windows Server Essentials ADK](../install/Getting-Started-with-the-Windows-Server-Essentials-ADK.md)   
 [Criando e personalizando a imagem](../install/Creating-and-Customizing-the-Image.md)   
 [Personalizações adicionais](../install/Additional-Customizations.md)   
 [Preparando a imagem para implantação](../install/Preparing-the-Image-for-Deployment.md)   
 [Testando a experiência do usuário](../install/Testing-the-Customer-Experience.md)

