---
title: Preparar seu ambiente para o Windows Admin Center
description: Preparar seu ambiente para o Windows Admin Center (Project Honolulu)
ms.technology: manage
ms.topic: article
author: nwashburn-ms
ms.author: niwashbu
ms.date: 06/07/2019
ms.localizationpriority: medium
ms.prod: windows-server
ms.openlocfilehash: 72e71ce2d1427f392aa02d32597f92d031f9a5c9
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71407003"
---
# <a name="prepare-your-environment-for-windows-admin-center"></a>Preparar seu ambiente para o Windows Admin Center

> Aplica-se a: Windows Admin Center, Versão prévia do Windows Admin Center

Há algumas versões de servidor que precisam de preparação adicional antes de serem prontos para gerenciar com o Windows Admin Center:

- [Windows Server 2012 e 2012 R2](#prepare-windows-server-2012-and-2012-r2)
- [Windows Server 2008 R2](#prepare-windows-server-2008-r2)
- [Microsoft Hyper-V Server 2016](#prepare-microsoft-hyper-v-server-2016)
- [Microsoft Hyper-V Server 2012 R2](#prepare-microsoft-hyper-v-server-2012-r2)

Também há alguns cenários em que a [configuração de porta no servidor de destino](#port-configuration-on-the-target-server) pode precisar ser modificada antes de gerenciar com o centro de administração do Windows.

## <a name="prepare-windows-server-2012-and-2012-r2"></a>Preparar o Windows Server 2012 e 2012 R2

### <a name="install-wmf-version-51-or-higher"></a>Instalar o WMF versão 5.1 ou posterior

O Windows Admin Center exige recursos do PowerShell que não estão incluídos por padrão no Windows Server 2012 e 2012 R2. Para gerenciar o Windows Server 2012 ou 2012 R2 com o Windows Admin Center, você precisará instalar o WMF versão 5.1 ou posterior nesses servidores.

Digite `$PSVersiontable` no PowerShell para verificar se o WMF está instalado e se a versão é 5.1 ou superior.

Se não estiver instalado, você pode [baixar e instalar 5.1 WMF](https://docs.microsoft.com/powershell/wmf/setup/install-configure).

## <a name="prepare-windows-server-2008-r2"></a>Preparar o Windows Server 2008 R2

### <a name="install-wmf-version-51-or-higher"></a>Instalar o WMF versão 5.1 ou posterior

O Windows Admin Center exige recursos do PowerShell que não estão incluídos por padrão no Windows Server 2008 R2. Para gerenciar o Windows Server 2008 R2 com o Windows Admin Center, você precisará instalar o WMF versão 5.1 ou posterior nesses servidores. 

Verifique se o [.NET Framework 4.5.2 ou posterior](https://docs.microsoft.com/dotnet/framework/install/on-windows-7) já está instalado no computador.

Digite `$PSVersiontable` no PowerShell para verificar se o WMF está instalado e se a versão é 5.1 ou superior.

Se não estiver instalado, você pode [baixar e instalar 5.1 WMF](https://docs.microsoft.com/powershell/wmf/setup/install-configure).

Execute `Enable-PSRemoting –force` em um console do PowerShell para habilitar a conexão remota do Powershell. 

### <a name="enable-remote-desktop"></a>Habilitar a área de trabalho remota

Para usar a área de trabalho remota no Windows Admin Center, você deverá habilitar a Área de trabalho remota no seu servidor do Windows Server 2008 R2.

No **Gerenciador do Servidor**, vá para **Configurar área de trabalho remota**. Habilite a área de trabalho remota para "Permitir conexões de computadores executando qualquer versão da área de trabalho remota".

## <a name="prepare-microsoft-hyper-v-server-2016"></a>Preparar o Microsoft Hyper-V Server 2016

Para gerenciar o Microsoft Hyper-V Server 2016 com o Windows Admin Center, há algumas funções de servidor, que você precisará habilitar antes que você pode fazê-lo.

### <a name="to-manage-microsoft-hyper-v-server-2016-with-windows-admin-center"></a>Para gerenciar o Microsoft Hyper-V Server 2016 com o Windows Admin Center:

1. Habilite o gerenciamento remoto.
2. Habilite a função de servidor de arquivo.
3. Habilite o módulo do Hyper-V para o PowerShell.

### <a name="step-1-enable-remote-management"></a>**Etapa 1:** Habilitar o gerenciamento remoto

Para habilitar o gerenciamento remoto no Hyper-V Server.

1. Faça logon no servidor Hyper-V.
2. Na ferramenta de **Configuração do Servidor** (SCONFIG), digite **4** para configurar o gerenciamento remoto.
3. Digite **1** para habilitar o gerenciamento remoto.
4. Digite **4** para retornar ao menu principal.

### <a name="step-2-enable-file-server-role"></a>**Etapa 2:** Habilitar a função de servidor de arquivo

Para habilitar a função de servidor de arquivos para o gerenciamento remoto e compartilhamento de arquivos básico:

1. Clique em **Funções e recursos** no menu **Ferramentas** .
2. Em **Funções e recursos**, encontre **Arquivo e Serviços de armazenamento** e marque **Arquivo e serviços de iSCSI** e **Servidor de arquivos**:

![Captura de tela de funções e recursos mostrando a função de serviços de arquivo e iSCSI selecionada](../media/prepare-environment/c6c30b812d96afcc1edcdb6f52f0e13c.png)

### <a name="step-3-enable-hyper-v-module-for-powershell"></a>**Etapa 3:** Habilitar o módulo do Hyper-V para o PowerShell

Para habilitar o módulo do Hyper-V para recursos do PowerShell:

1. Clique em **Funções e recursos** no menu **Ferramentas** .
2. Em **Funções e recursos**, encontre as **Ferramentas de administração de servidor remoto** e marque **Ferramentas de administração de função** e **Módulo do Hyper-V para PowerShell**:

![Captura de tela de funções e recursos mostrando funções do Hyper-V selecionadas](../media/prepare-environment/7ab0999602b7083733525bd0c1ba2747.png)

O Microsoft Hyper-V Server 2016 agora está pronto para o gerenciamento com o Windows Admin Center.

## <a name="prepare-microsoft-hyper-v-server-2012-r2"></a>Preparar o Microsoft Hyper-V Server 2012 R2

Para gerenciar o Microsoft Hyper-V Server 2012 R2 com o Windows Admin Center, há algumas funções de servidor que você deverá habilitar antes.  Além disso, você deverá instalar o WMF versão 5.1 ou posterior.

### <a name="to-manage-microsoft-hyper-v-server-2012-r2-with-windows-admin-center"></a>Para gerenciar o Microsoft Hyper-V Server 2012 R2 com o Windows Admin Center:

1. Instalar o Windows Management Framework (WMF) versão 5.1 ou posterior
2. Habilitar o gerenciamento remoto
3. Habilitar a função de servidor de arquivo
4. Habilitar o módulo do Hyper-V para o PowerShell

### <a name="step-1-install-windows-management-framework-51"></a>Etapa 1: Instalar o Windows Management Framework 5,1

Requer o Windows Admin Center PowerShell recursos que não estão incluídos por padrão no Microsoft Hyper-V Server 2012 R2. Para gerenciar o Microsoft Hyper-V Server 2012 R2 com o Windows Admin Center, você precisará instalar WMF versão 5.1 ou posterior.

Digite `$PSVersiontable` no PowerShell para verificar se o WMF está instalado e se a versão é 5.1 ou superior. 

Se não estiver instalado, você pode [baixar o WMF 5.1](https://docs.microsoft.com/powershell/wmf/setup/install-configure).

### <a name="step-2-enable-remote-management"></a>Etapa 2: Habilitar o gerenciamento remoto

Para habilitar o gerenciamento remoto do Hyper-V Server.

1. Faça logon no servidor Hyper-V.
2. Na ferramenta de **Configuração do Servidor** (SCONFIG), digite **4** para configurar o gerenciamento remoto.
3. Digite **1** para habilitar o gerenciamento remoto.
4. Digite **4** para retornar ao menu principal.

### <a name="step-3-enable-file-server-role"></a>Etapa 3: Habilitar a função de servidor de arquivo

Para habilitar a função de servidor de arquivos para o gerenciamento remoto e compartilhamento de arquivos básico:

1. Clique em **Funções e recursos** no menu **Ferramentas** .
2. Em **Funções e recursos**, encontre **Arquivo e serviços de armazenamento** e marque **Arquivo e serviços de iSCSI** e **Servidor de arquivos**:

![Captura de tela de funções e recursos mostrando a função de serviços de arquivo e iSCSI selecionada](../media/prepare-environment/c6c30b812d96afcc1edcdb6f52f0e13c.png)

### <a name="step-4-enable-hyper-v-module-for-powershell"></a>Etapa 4: Habilitar o módulo do Hyper-V para o PowerShell

Para habilitar o módulo do Hyper-V para recursos do PowerShell:

1. Clique em **Funções e recursos** no menu **Ferramentas** .
2. Em **Funções e recursos**, encontre as **Ferramentas de administração de servidor remoto** e marque **Ferramentas de administração de função** e **Módulo do Hyper-V para PowerShell**:

![Captura de tela de funções e recursos mostrando as ferramentas de administração de servidor remoto do Hyper-V selecionadas](../media/prepare-environment/7ab0999602b7083733525bd0c1ba2747.png)

O Microsoft Hyper-V Server 2012 R2 agora está pronto para o gerenciamento com o Windows Admin Center.

## <a name="port-configuration-on-the-target-server"></a>Configuração de porta no servidor de destino

O centro de administração do Windows usa o protocolo de compartilhamento de arquivos SMB para algumas tarefas de cópia de arquivos, como ao importar um certificado em um servidor remoto. Para que essas operações de cópia de arquivo tenham sucesso, o firewall no servidor remoto deve permitir conexões de entrada na porta 445.  Você pode usar a ferramenta de firewall no centro de administração do Windows para verificar se a regra de entrada para ' gerenciamento remoto de servidor de arquivos (SMB-in) ' está definida para permitir o acesso nesta porta.

> [!Tip]
> Pronto para instalar o Windows Admin Center? [Baixar agora](https://docs.microsoft.com/windows-server/manage/windows-admin-center/understand/windows-admin-center#download-now)
