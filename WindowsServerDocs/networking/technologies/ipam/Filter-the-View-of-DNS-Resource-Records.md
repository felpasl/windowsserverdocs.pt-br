---
title: Filtrar a exibição de registros de recursos de DNS
description: Este tópico faz parte do guia de gerenciamento do IPAM (gerenciamento de endereços IP) no Windows Server 2016.
manager: brianlic
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: networking-ipam
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5b80294a-7325-476b-84eb-69f0d051e8b2
ms.author: pashort
author: shortpatti
ms.openlocfilehash: 541645a274481bb8b044c37df572d7746c5da30e
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71405662"
---
# <a name="filter-the-view-of-dns-resource-records"></a>Filtrar a exibição de registros de recursos de DNS

>Aplica-se a: Windows Server (Canal Semestral), Windows Server 2016

Você pode usar este tópico para filtrar a exibição de registros de recursos de DNS no console do cliente IPAM.  
  
A associação em **Administradores**, ou equivalente, é o requisito mínimo para executar este procedimento.  
  
### <a name="to-filter-the-view-of-dns-resource-records"></a>Para filtrar a exibição de registros de recursos de DNS  
  
1.  Em Gerenciador do Servidor, clique em **IPAM**. O console do cliente IPAM é exibido.  
  
2.  No painel de navegação, em **monitorar e gerenciar**, clique em **zonas DNS**.  O painel de navegação divide-se em um painel de navegação superior e em um painel de navegação inferior.  
  
3.  No painel de navegação inferior, clique em **pesquisa direta**. Todas as zonas de pesquisa direta do DNS gerenciadas pelo IPAM são exibidas nos resultados da pesquisa do painel de exibição.  
  
4.  Clique na zona cujos registros você deseja exibir e filtrar.  
  
5.  No painel de exibição, clique em **exibição atual**e em **registros de recursos**. Os registros de recursos para a zona são mostrados no painel de exibição.  
  
6.  No painel de exibição, clique em **Adicionar critérios**.  
  
    ![Adicionar critérios](../../media/Filter-the-View-of-DNS-Resource-Records/ipam_FilterRR_01.jpg)  
  
7.  Selecione um critério na lista suspensa. Por exemplo, se você quiser exibir um tipo de registro específico, clique em **tipo de registro**.  
  
    ![Selecionar um critério](../../media/Filter-the-View-of-DNS-Resource-Records/ipam_FilterRR_02.jpg)  
  
8.  Clique em **Adicionar** .  
  
    ![Adicionar os critérios](../../media/Filter-the-View-of-DNS-Resource-Records/ipam_FilterRR_03.jpg)  
  
9. O **tipo de registro** é adicionado como um parâmetro de pesquisa. Insira o texto para o tipo de registro que você deseja localizar. Por exemplo, se você quiser exibir somente os registros SRV, digite **SRV**.  
  
    ![Especifique o tipo de registro que você deseja localizar](../../media/Filter-the-View-of-DNS-Resource-Records/ipam_FilterRR_04.jpg)  
  
10. Pressione ENTER. Os registros de recurso DNS são filtrados de acordo com os critérios e a frase de pesquisa que você especificou.  
  
    ![Executar o filtro](../../media/Filter-the-View-of-DNS-Resource-Records/ipam_FilterRR_05.jpg)  
  
## <a name="see-also"></a>Consulte também  
[Gerenciamento de registros de recursos de DNS](DNS-Resource-Record-Management.md)  
[Gerenciar IPAM](Manage-IPAM.md)  
  


