---
title: Problemas conhecidos de ativação da MAK
description: Descreve problemas comuns que podem ocorrer durante o processo de ativação da MAK e oferece resoluções e diretrizes
ms.topic: article
ms.date: 10/3/2019
ms.technology: server-general
ms.assetid: ''
author: Teresa-Motiv
ms.author: v-tea
manager: dcscontentpm
ms.localizationpriority: medium
ms.openlocfilehash: 25fa6d32571597136580afe062aa8d9c7e2d82b7
ms.sourcegitcommit: 9855d6b59b1f8722f39ae74ad373ce1530da0ccf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71962982"
---
# <a name="mak-activation-known-issues"></a>Ativação da MAK: problemas conhecidos

Este artigo descreve problemas comuns que podem ocorrer durante as ativações da MAK (chave de ativação múltipla) e fornece diretrizes para resolver esses problemas.

## <a name="how-can-i-tell-whether-my-computer-is-activated"></a>Como posso saber se meu computador está ativado?

No computador, abra o controle do **Sistema** e procure **O Windows está ativado**. Como alternativa, execute Slmgr.vbs e use a opção de linha de comando **/dli**.

## <a name="the-computer-does-not-activate-over-the-internet"></a>O computador não é ativado pela Internet

Verifique se as portas necessárias estão abertas no firewall. Para obter uma lista de portas, confira o [Guia de implantação de ativação de volume](http://go.microsoft.com/fwlink/?linkid=150083).

## <a name="internet-and-telephone-activation-fail"></a>Falha na ativação pela Internet e por telefone

Entre em contato com o Centro de Ativação Microsoft local. Para obter os números telefônicos do Centro de Ativação Microsoft em todo o mundo, acesse [Números de telefone em todo o mundo dos Centros de Ativação de Licenciamento da Microsoft](https://www.microsoft.com/Licensing/existing-customer/activation-centers). Forneça as informações do Contrato de licença de volume e do recibo da compra quando você ligar.

## <a name="slmgrvbs-ato-returns-an-error-code"></a>Slmgr.vbs /ato retorna um código de erro

Se Slmgr.vbs retornar um código de erro hexadecimal, determine a mensagem de erro correspondente executando o seguinte script:

```cmd
slui.exe 0x2a 0x <ErrorCode>
```

Para obter mais informações sobre códigos de erro específicos e como resolvê-los, confira [Resolver códigos de erro de ativação comuns](activation-error-codes.md).
