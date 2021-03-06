---
title: Delegar permissões de gerenciamento para Namespaces DFS
description: Este artigo descreve como delegar permissões de gerenciamento para namespaces DFS e quais grupos podem executar tarefas de namespace por padrão
ms.date: 6/5/2017
ms.prod: windows-server
ms.technology: storage
ms.topic: article
author: JasonGerend
manager: brianlic
ms.author: jgerend
ms.openlocfilehash: 5bf23498c95d4b44d5c17aecd216921dc70819a3
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71402220"
---
# <a name="delegate-management-permissions-for-dfs-namespaces"></a>Delegar permissões de gerenciamento para Namespaces DFS

> Aplica-se a: Windows Server 2019, Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008

A tabela a seguir descreve os grupos que podem realizar tarefas básicas de namespace por padrão e o método para delegar a capacidade de executar essas tarefas:

|Tarefa | Grupos que podem executar essa tarefa por padrão | Método de delegação |
|---|---|---|
|Criar um novo namespace baseado em domínio|Grupo de administradores de domínio no domínio em que o namespace está configurado|Clique com o botão direito no nó **Namespaces**, na árvore de console e depois clique em **Delegar permissões de gerenciamento**. Ou use o [Set-DfsnRoot GrantAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot) e [Set-DfsnRoot RevokeAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot). Cmdlets do Windows PowerShell (apresentados no Windows Server 2012). Você também deve adicionar o usuário ao grupo local Administradores no servidor de namespace.|
|Adicionar servidores de namespace para um namespace baseado em domínio|Grupo de administradores de domínio no domínio em que o namespace está configurado| Clique com o botão direito no namespace baseado em domínio na árvore de console e depois clique em **Delegar permissões de gerenciamento**. Ou use o [Set-DfsnRoot GrantAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot) e [Set-DfsnRoot RevokeAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot). Cmdlets do Windows PowerShell (apresentados no Windows Server 2012). Você também deve adicionar o usuário ao grupo local Administradores no servidor de namespace a ser adicionado.|
|Gerenciar um novo namespace baseado em domínio|Grupo local de administradores em cada servidor de namespace| Clique com o botão direito no namespace baseado em domínio na árvore de console e depois clique em **Delegar permissões de gerenciamento**. |
|Criar um namespace autônomo|Grupo local de administradores no servidor do namespace| Adicione o usuário ao grupo local Administradores no servidor de namespace. |
|Gerenciar um namespace autônomo*|Grupo local de administradores no servidor do namespace| Clique com o botão direito no namespace autônomo na árvore de console e depois clique em **Delegar permissões de gerenciamento**. Ou use o [Set-DfsnRoot GrantAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot) e [Set-DfsnRoot RevokeAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot). Cmdlets do Windows PowerShell (apresentados no Windows Server 2012).|
|Criar um grupo de replicação ou habilitar a replicação DFS em uma pasta|Grupo de administradores de domínio no domínio em que o namespace está configurado| Clique com o botão direito no nó Replicação, na árvore de console e depois clique em **Delegar permissões de gerenciamento**. |

<br />

\*delegar permissões de gerenciamento para gerenciar um namespace autônomo não concede ao usuário a capacidade de exibir e gerenciar a segurança usando a guia **delegação** , a menos que o usuário seja membro do grupo Administradores local no servidor de namespace. Esse problema ocorre porque o snap-in do Gerenciamento DFS não pode recuperar as listas de controle de acesso discricionário (DACLs) para o namespace independente do registro. Para habilitar o snap-in para exibir informações de delegação, você deve seguir as etapas na Base de Dados de Conhecimento da Microsoft<sup>®</sup>: [KB314837: Como gerenciar acesso remoto ao registro](https://go.microsoft.com/fwlink?linkid=46803)