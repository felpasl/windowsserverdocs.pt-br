---
title: Inicializar o cluster HGS usando o modo de chave em uma floresta de bastiões
ms.custom: na
ms.prod: windows-server
ms.topic: article
manager: dongill
author: rpsqrd
ms.technology: security-guarded-fabric
ms.date: 08/29/2018
ms.openlocfilehash: e72de1c85e0a9c3decf1fd3b5085363b57ca387c
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71403636"
---
# <a name="initialize-the-hgs-cluster-using-key-mode-in-an-existing-bastion-forest"></a>Inicializar o cluster HGS usando o modo de chave em uma floresta de bastiões existente

> Aplica-se a: Windows Server 2019
> 
> [!div class="step-by-step"]
> [«Instalar o HgS em uma nova floresta](guarded-fabric-install-hgs-in-a-bastion-forest.md)
> [criar a chave do host»](guarded-fabric-create-host-key.md)

Active Directory Domain Services será instalado no computador, mas deverá permanecer não configurado.

[!INCLUDE [Obtain certificates for HGS](../../../includes/guarded-fabric-initialize-hgs-default-step-two.md)] 

Antes de continuar, verifique se você pré-testeu os objetos de cluster para o serviço guardião de host e concedeu ao usuário conectado **controle total** sobre os objetos VCO e CNO no Active Directory.
O nome do objeto de computador virtual precisa ser passado para o parâmetro `-HgsServiceName` e o nome do cluster para o parâmetro `-ClusterName`.

> [!TIP]
> Verifique novamente os controladores de domínio do AD para garantir que seus objetos de cluster tenham sido replicados para todos os DCs antes de continuar.

Se você estiver usando certificados baseados em PFX, execute os seguintes comandos no servidor HGS:

```powershell
$signingCertPass = Read-Host -AsSecureString -Prompt "Signing certificate password"
$encryptionCertPass = Read-Host -AsSecureString -Prompt "Encryption certificate password"

Install-ADServiceAccount -Identity 'HGSgMSA'

Initialize-HgsServer -UseExistingDomain -ServiceAccount 'HGSgMSA' -JeaReviewersGroup 'HgsJeaReviewers' -JeaAdministratorsGroup 'HgsJeaAdmins' -HgsServiceName 'HgsService' -ClusterName 'HgsCluster' -SigningCertificatePath '.\signCert.pfx' -SigningCertificatePassword $signPass -EncryptionCertificatePath '.\encCert.pfx' -EncryptionCertificatePassword $encryptionCertPass -TrustHostKey
```

Se você estiver usando certificados instalados no computador local (como certificados com suporte do HSM e certificados não exportáveis), use os parâmetros `-SigningCertificateThumbprint` e `-EncryptionCertificateThumbprint` em vez disso.

