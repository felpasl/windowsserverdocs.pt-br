---
title: Escolha entre pontos de verificação padrão ou de produção no Hyper-V
description: Fornece instruções para configurar uma máquina virtual para usar pontos de verificação padrão ou de produção
ms.prod: windows-server-threshold
ms.service: na
manager: dongill
ms.technology: compute-hyper-v
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 92bb573b-03b7-470e-b72e-e35edf52b349
author: KBDAzure
ms.author: kathydav
ms.date: 10/04/2016
ms.openlocfilehash: 239cce3c9f1acb2d45935e0f60fb1875b004485b
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59880947"
---
# <a name="choose-between-standard-or-production-checkpoints-in-hyper-v"></a>Escolha entre pontos de verificação padrão ou de produção no Hyper-V

>Aplica-se a: Windows 10, Windows Server 2016, Microsoft Hyper-V Server 2016, Windows Server 2019, Microsoft Hyper-V Server 2019

  
Começando com o Windows Server 2016 e Windows 10, você pode escolher entre pontos de verificação padrão e de produção para cada máquina virtual. Pontos de verificação de produção são o padrão para novas máquinas virtuais.
  
- Pontos de verificação de produção são imagens "pontuais" de uma máquina virtual, que podem ser restauradas posteriormente de forma que tem suporte completo para todas as cargas de trabalho de produção. Isso é obtido usando a tecnologia de backup no convidado para criar o ponto de verificação, em vez de usar a tecnologia de estado salvo.  
  
- Pontos de verificação padrão capturam a configuração de estado, dados e hardware de uma máquina virtual em execução e se destinam para uso em cenários de desenvolvimento e teste. Pontos de verificação padrão podem ser útil se você precisar recriar um estado específico ou uma condição de uma máquina virtual em execução para que você pode solucionar um problema.  
 
 ## <a name="change-checkpoints-to-production-or-standard-checkpoints"></a>Alterar os pontos de verificação de produção ou pontos de verificação padrão  
  
1.  Na **Gerenciador do Hyper-V**, clique com botão direito na máquina virtual e clique em **configurações**.  
  
2.  Sob o **Management** seção, selecione **pontos de verificação**.  
  
3.  Selecione pontos de verificação de produção ou padrão.  
  
    Se você escolher pontos de verificação de produção, você também pode especificar se o host deve obter um ponto de verificação padrão se um ponto de verificação de produção não pode ser usado. Se você desmarcar essa caixa de seleção e um ponto de verificação de produção não pode ser usado, nenhum ponto de verificação é executado.  
  
4.  Se você deseja armazenar os arquivos de configuração do ponto de verificação em um local diferente, alterá-la na **local do arquivo de ponto de verificação** seção.  
  
5.  Clique em **aplicar** para salvar suas alterações. Se você tiver terminado, clique em **Okey** para fechar a caixa de diálogo.  
  
> [!NOTE]
> Somente **pontos de verificação de produção** têm suporte nos convidados que executam a função de serviços de domínio do Active Directory (controlador de domínio) ou a função do Active Directory Lightweight Directory Services.

## <a name="see-also"></a>Consulte também  
  
-   [Pontos de verificação de produção](../What-s-new-in-Hyper-V-on-Windows.md#BKMK_check)  
  
-   [Habilitar ou desabilitar os pontos de verificação](Enable-or-disable-checkpoints-in-Hyper-V.md)  
  

