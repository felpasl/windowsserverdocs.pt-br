---
ms.assetid: c9844427-27cf-4d76-b5bb-e06368b092f7
title: Clustering de failover
ms.prod: windows-server-threshold
layout: LandingPage
ms.topic: landing-page
ms.manager: dongill
author: JasonGerend
ms.author: jgerend
ms.technology: storage-failover-clustering
ms.date: 06/06/2019
ms.localizationpriority: high
ms.openlocfilehash: a7f6dd847d2762dbc616189ed729449479788f98
ms.sourcegitcommit: 6ef4986391607bb28593852d06cc6645e548a4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66810908"
---
# <a name="failover-clustering-in-windows-server"></a>Clustering de failover no Windows Server

> Aplica-se a: Windows Server 2019, Windows Server 2016

Um cluster de failover é um conjunto de computadores independentes que trabalham em conjunto para aumentar a disponibilidade e escalabilidade de funções de cluster (antigamente chamadas de aplicações e serviços de cluster). Os servidores clusterizados (chamados de nós) são conectados por cabos físicos e por software. Se um ou mais dos nós do cluster falhar, o outro nó começará a fornecer o serviço (um processo conhecido como failover). Além disso, as funções de cluster são monitoradas de maneira proativa para verificar se estão funcionando adequadamente. Se o funcionamento não estiver correto, elas serão reiniciadas ou movidas para outro nó.

Os clusters de failover também fornecem a funcionalidade CSV (Volume Compartilhado Clusterizado) que, por sua vez, oferece um namespace consistente distribuído, o qual pode ser usado para acessar o armazenamento compartilhado em todos os nós. Com o recurso Clustering de Failover, os usuários passam pelo mínimo de interrupções no serviço.

O clustering de failover tem muitos aplicativos práticos, incluindo:

* Armazenamento de compartilhamento de arquivos altamente disponível ou continuamente disponível para aplicativos como máquinas virtuais de Microsoft SQL Server e Hyper-V
* Funções clusterizadas com alta disponibilidade que são executadas em servidores físicos ou em máquinas virtuais instaladas em servidores que executam o Hyper-V

| **Entender**                                                               |  **Planejamento**                          |  **Implantação**       |
| -------------                                                                |  --------------                        | --------------------- |
| [Novidades no clustering de failover](whats-new-in-failover-clustering.md)    | [Planejamento de requisitos de Hardware de Clustering de Failover e opções de armazenamento](clustering-requirements.md)  | [Criando um Cluster de Failover](create-failover-cluster.md) |
| [Servidor de arquivos de escalabilidade horizontal para dados de aplicativos](sofs-overview.md)               | [Usar CSVs (Volumes Compartilhados do Cluster)](failover-cluster-csvs.md) | [Implantar um servidor de arquivos com dois nós](../storage/storage-spaces/storage-spaces-direct-in-vm.md) |
|  [Quorum de cluster e pool](../storage/storage-spaces/understand-quorum.md)   |  [Usando clusters convidados da máquina virtual com espaços de armazenamento diretos](../storage/storage-spaces/storage-spaces-direct-in-vm.md)       | [Pré-configurar os objetos de computador do cluster nos serviços de domínio do Active Directory](prestage-cluster-adds.md) |
| [Reconhecimento de domínio de falha](fault-domains.md)                                 |                                 | [Configuração de contas de cluster no Active Directory](configure-ad-accounts.md) |
| [SMB Multichannel simplificado e redes de cluster de várias NICs](smb-multichannel.md) |                       | [Gerenciar o quorum e testemunhas](manage-cluster-quorum.md) |
| [Balanceamento de carga de VM](vm-load-balancing-overview.md)                         |                             | [Implantar uma testemunha de nuvem](deploy-cloud-witness.md) |
| [Conjuntos de cluster](../storage/storage-spaces/cluster-sets.md)                  |                             |[Implantar testemunha de compartilhamento de arquivos](file-share-witness.md) |
| [Afinidade de cluster](cluster-affinity.md)                                     |                            | [Atualizações sem interrupção do sistema operacional do cluster](cluster-operating-system-rolling-upgrade.md) |
|                                                                             |                            | [Atualizar um cluster de failover no mesmo hardware](upgrade-option-same-hardware.md) |
|                                                                            |                             | [Implantar um Cluster desanexado do Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265970\(v%3dws.11\))

|**Gerenciar**  |  **Ferramentas e configurações**  |  **Recursos da comunidade**       |
| ------------- |  -------------- | --------------------- |
| [Atualização com suporte a cluster](cluster-aware-updating.md)    |   [Cmdlets do PowerShell de Clustering de failover](https://docs.microsoft.com/powershell/module/failoverclusters/?view=win10-ps)      |  [Fórum sobre alta disponibilidade (Clustering)](https://go.microsoft.com/fwlink/p/?LinkId=230641)       |
|  [Serviço de integridade](health-service-overview.md)   |   [Com suporte a Cmdlets de PowerShell de atualização de cluster](https://docs.microsoft.com/powershell/module/clusterawareupdating/?view=win10-ps)      | [Blog da equipe balanceamento de carga de rede e Clustering de failover](http://blogs.msdn.com/b/clustering/)        |
|  [Migração de domínio do cluster](cluster-domain-migration.md)   |         |         |
|  [Solução de problemas usando o Relatório de Erros do Windows](troubleshooting-using-wer-reports.md)   |         |         |