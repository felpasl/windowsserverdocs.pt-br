---
title: Proteger o volume do sistema com proteção de disco
description: Fornece informações sobre a proteção de disco para serviços do MultiPoint
ms.custom: na
ms.date: 07/22/2016
ms.prod: windows-server
ms.technology: multipoint-services
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 18694665-ed65-4d84-8505-f460cf3df907
author: evaseydl
manager: scotman
ms.author: evas
ms.openlocfilehash: 27bcce68cfe5856e987f5ad93460abd12217c26b
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71389513"
---
# <a name="protecting-the-system-volume-with-disk-protection"></a>Proteger o volume do sistema com proteção de disco
Os serviços do MultiPoint fornecem a opção de apagar instantaneamente todas as alterações no volume do sistema sempre que o computador for iniciado. Se você habilitar o recurso de proteção de disco, quaisquer modificações na unidade, como corrupção de configuração ou introdução de malware, serão desfeitas na próxima vez que o computador for reiniciado. Esse é um recurso conveniente para os administradores que desejam garantir que uma imagem de software "boa" ou "ouro" conhecida seja carregada todas as vezes. Atualizações automáticas ou aplicação de patch de software podem ser agendadas, por exemplo, no meio da noite. A consideração de planejamento é se você deseja que os usuários finais possam fazer alterações, como instalar software da Internet. Com esse recurso habilitado, se você quiser que os usuários possam armazenar arquivos, o compartilhamento de arquivos deverá estar fora do volume do sistema.  
  
