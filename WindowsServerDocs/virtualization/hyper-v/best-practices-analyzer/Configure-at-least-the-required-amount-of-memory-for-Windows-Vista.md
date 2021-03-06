---
title: Configure pelo menos a quantidade necessária de memória para uma máquina virtual que executa o Windows Vista e esteja habilitada para Memória Dinâmica
description: Versão online do texto para esta regra de Analisador de Práticas Recomendadas.
ms.prod: windows-server
ms.service: na
manager: dongill
ms.technology: compute-hyper-v
ms.author: kathydav
ms.topic: article
ms.assetid: d3de7614-6eee-4839-a939-d390bca9ba89
author: KBDAzure
ms.date: 8/16/2016
ms.openlocfilehash: d86510f0676c4d542f43d73cc8a5607aabfb3e18
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71366372"
---
# <a name="configure-at-least-the-required-amount-of-memory-for-a-virtual-machine-running-windows-vista-and-enabled-for-dynamic-memory"></a>Configure pelo menos a quantidade necessária de memória para uma máquina virtual que executa o Windows Vista e esteja habilitada para Memória Dinâmica

>Aplica-se a: Windows Server 2016

Para obter mais informações sobre práticas recomendadas e verificações, consulte [executar verificações de analisador de práticas recomendadas e gerenciar resultados de verificação](https://go.microsoft.com/fwlink/p/?LinkID=223177).  
  
|Propriedade|Detalhes|  
|-|-|  
|**Sistema Operacional**|Windows Server 2016|  
|**Produto/recurso**|Hyper-V|  
|**Severity**|Erro|  
|**Categorias**|Configuração|  
  
Nas seções a seguir, os itálicos indicam o texto da interface do usuário que aparece na ferramenta de Analisador de Práticas Recomendadas para esse problema.  
  
## <a name="issue"></a>Problema  
*Uma ou mais máquinas virtuais estão configuradas para usar Memória Dinâmica com menos do que a quantidade de memória necessária para o Windows Vista.*  
  
## <a name="impact"></a>Impacto  
*O sistema operacional convidado nas seguintes máquinas virtuais pode não ser executado ou pode ser executado de forma não confiável:*  
  
\<list de máquinas virtuais >  
  
## <a name="resolution"></a>Resolução  
*Use o Gerenciador do Hyper-V ou o Windows PowerShell para aumentar a memória mínima para pelo menos 256 MB e a memória de inicialização e máxima para pelo menos 512 MB.*  
  
### <a name="increase-memory-using-hyper-v-manager"></a>Aumentar a memória usando o Gerenciador do Hyper-V  
  
1.  Abra o Gerenciador Hyper-V. (Em Gerenciador do Servidor, clique em **ferramentas** > **Gerenciador do Hyper-V**.)  
  
2.  Na lista de máquinas virtuais, clique com o botão direito do mouse no que você deseja e clique em **configurações**.  
  
3.  No painel de navegação, clique em **memória**.  
  
4.  Altere a **RAM** para pelo menos 512 MB.  
  
5.  Em **memória dinâmica**, altere o **mínimo de RAM** para pelo menos 256 MB e o **máximo de RAM** para 512 MB.  
  
6.  Clique em **OK**.  
  
### <a name="increase-memory-using-windows-powershell"></a>Aumentar a memória usando o Windows PowerShell  
  
1.  Abra o Windows PowerShell. (Na área de trabalho, clique em **Iniciar** e comece a digitar **Windows PowerShell**.)  
  
2.  Clique com o botão direito do mouse em **Windows PowerShell** e clique em **Executar como administrador**.  
  
3.  Execute um comando semelhante ao seguinte, substituindo MyVM pelo nome da sua máquina virtual e os valores de memória com pelo menos os valores mostrados abaixo.  
  
```  
Get-VM MyVM | Set-VMMemory -DynamicMemoryEnabled $True -MaximumBytes 512MB -MinimumBytes 256MB -StartupBytes 512MB  
```  
  


