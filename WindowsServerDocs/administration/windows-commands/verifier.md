---
title: verifier
description: 'Tópico de comandos do Windows para * * * *- '
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 782173d6-f196-4bc4-a547-76109829453c
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: cc2482fa25d0236991889c3951cb522e27bf520d
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71362693"
---
# <a name="verifier"></a>verifier

>Aplica-se a: Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Gerenciador de verificação de driver.  

## <a name="syntax"></a>Sintaxe  
```  
verifier /standard /driver <name> [<name> ...]  
verifier /standard /all  
verifier [/flags <flags>] [/faults [<probability> [<tags> [<applications> [<minutes>]]]] /driver <name> [<name>...]  
verifier [/flags FLAGS] [/faults [<probability> [<tags> [<applications> [<minutes>]]]] /all  
verifier /querysettings  
verifier /volatile /flags <flags>  
verifier /volatile /adddriver <name> [<name>...]  
verifier /volatile /removedriver <name> [<name>...]  
verifier /volatile /faults [<probability> [<tags> [<applications>]]  
verifier /reset  
verifier /query  
verifier /log <LogFileName> [/interval <seconds>]  
```  
### <a name="parameters"></a>Parâmetros  
|Parâmetro|Descrição|  
|-------|--------|  
|\<flags >|Deve ser um número em decimal ou hexadecimal, combinação de bits:<br /><br />Valor -    **: Descrição**<br />-   **bit 0:** verificação de pool especial<br />-   **bit 1:** forçar verificação de IRQL<br />-   **bit 2:** simulação de recursos baixos<br />-   **bit 3:** rastreamento de pool<br />-   **bit 4:** Verificação de e/s<br />-   **bit 5:** detecção de deadlock<br />-   **bit 6:** não usado<br />-   **bit 7:** Verificação de DMA<br />-   **bit 8:** verificações de segurança<br />-   **bit 9:** forçar solicitações de e/s pendentes<br />-   **bit 10:** Log de IRP<br />-   **bit 11:** verificações diversas<br /><br />por exemplo, **/flags 27** é equivalente a **/flags 0x1B**|  
|/volatile|Usado para alterar as configurações do verificador dinamicamente sem reiniciar o sistema. As novas configurações serão perdidas quando o sistema for reiniciado.|  
|\<probability >|Número entre 1 e 10.000 especificando a probabilidade de injeção de falha. Por exemplo, especificar 100 significa uma probabilidade de injeção de falha de 1% (100/10000).<br /><br />Se esse parâmetro não for especificado, a probabilidade padrão de 6% será usada.|  
|\<tags >|Especifica as marcas de pool que serão injetadas com falhas, separadas por caracteres de espaço. Se esse parâmetro não for especificado, qualquer alocação de pool poderá ser injetada com falhas.|  
|\<applications >|Especifica o nome do arquivo de imagem dos aplicativos que serão injetados com falhas, separados por caracteres de espaço. Se esse parâmetro não for especificado, a simulação de recursos Baixos poderá ocorrer em qualquer aplicativo.|  
|\<minutes >|Um número positivo que especifica o comprimento do período após a reinicialização, em minutos, durante o qual nenhuma injeção de falha ocorrerá. Se esse parâmetro não for especificado, o comprimento padrão de 8 minutos será usado.|  
|/?|Exibe a ajuda no prompt de comando.|  

## <a name="additional-references"></a>Referências adicionais  
-   [Chave da sintaxe de linha de comando](command-line-syntax-key.md)  