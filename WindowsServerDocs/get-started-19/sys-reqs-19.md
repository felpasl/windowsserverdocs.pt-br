---
title: Requisitos de sistema do Windows Server de 2019
description: Requisitos mínimos para armazenamento, CPU, rede, memória, RAM em uma instalação limpa do Windows Server 2019.
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: server-general
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 4a8b42d7-9fe5-4efe-9ea1-ace2131f860e
author: coreyp-at-msft
ms.author: coreyp
manager: jasgroce
ms.localizationpriority: medium
ms.openlocfilehash: d97ec0efee86165f82bdf99a316d24d9c39ec958
ms.sourcegitcommit: 6ef4986391607bb28593852d06cc6645e548a4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66810721"
---
# <a name="system-requirements"></a>Requisitos do sistema

>Aplica-se a: Windows Server 2019 

Este tópico descreve os requisitos mínimos do sistema para executar o Windows Server&reg; 2019.

## <a name="review-system-requirements"></a>Examine os requisitos de sistema  

Estes são os requisitos de sistema estimados 2019 do Windows Server. Se o seu computador não atender aos requisitos "mínimos", não será possível instalar este produto corretamente. Os requisitos reais variam conforme a configuração do sistema e dos aplicativos e recursos instalados.

Salvo indicação em contrário, esses requisitos mínimos de sistema aplicam-se a todas as opções de instalação (Server Core, Server com Experiência Desktop e Nano Server) e às edições Standard e Datacenter.  

> [!IMPORTANT]  
> O escopo muito diversificado de possíveis implantações inviabiliza a determinação de requisitos de sistema "recomendados" para aplicação geral. Consulte a documentação de cada função de servidor a ser implantada para obter mais detalhes sobre os recursos necessários a determinadas funções de servidor. Para obter os melhores resultados, realize implantações de teste para determinar os requisitos de sistema adequados aos cenários da sua implantação em particular.  

## <a name="processor"></a>Processador  

O desempenho do processador depende não apenas da frequência do relógio do processador, mas também do número de núcleos e do tamanho do cache do processador. Os requisitos de processador para este produto são:  

**Mínimo**:  
- Processador de 1,4 GHz e 64 bits  
- Compatível com conjunto de instruções de x64  
- Oferece suporte a NX e DEP  
- Oferece suporte a CMPXCHG16b, LAHF/SAHF e PrefetchW  
- Oferece suporte à Conversão de endereços de segundo nível (EPT ou NPT)  

[Coreinfo](https://technet.microsoft.com/sysinternals/cc835722.aspx) é uma ferramenta que você pode usar para confirmar quais desses recursos sua CPU possui.

## <a name="ram"></a>RAM  
Os requisitos estimados de RAM para este produto são:  

**Mínimo**:  
- 512 MB (2 GB para a opção de instalação Servidor com Experiência Desktop)
- Tipo ECC (código de correção de erro) ou tecnologia semelhante, para implantações de host físico

> [!IMPORTANT]  
> Se você criar uma máquina virtual com os parâmetros mínimos de hardware com suporte (1 núcleo do processador e 512 MB de RAM) e, em seguida, tentar instalar esta versão na máquina virtual, a instalação falhará.  
>   
> Para evitar isso, siga um destes procedimentos:  
>   
> -   Aloque mais de 800 MB de RAM para a máquina virtual em que você pretende instalar esta versão. Uma vez que a instalação for sido concluída, você poderá alterar a alocação para até 512 MB de RAM, dependendo da configuração do servidor real.  
> -   Interrompa o processo de inicialização desta versão na máquina virtual com SHIFT+F10. No prompt de comando que será aberto, use Diskpart.exe para criar e formatar uma partição de instalação. Execute **Wpeutil createpagefile /path=C:\pf.sys** (presumindo que a partição de instalação que você criou tenha sido C:). Feche o prompt de comando e prossiga com a instalação.  

## <a name="storage-controller-and-disk-space-requirements"></a>Controlador de armazenamento e requisitos de espaço em disco  
Computadores que executam o Windows Server 2019 devem incluir um adaptador de armazenamento que está em conformidade com a especificação de arquitetura PCI Express. Os dispositivos de armazenamento persistentes em servidores classificados como unidades de disco rígido não devem ser PATA. 2019 do Windows Server não permite ATA/PATA/IDE/EIDE para unidades de inicialização, página ou dados.  

Estes são os requisitos de espaço em disco **mínimos** estimados para a partição do sistema.  

**Mínimo**: 32 GB  

> [!NOTE]
> Esteja ciente de que o valor 32 GB deve ser considerado um *valor mínimo absoluto* para uma instalação bem-sucedida. Este mínimo deve permitir que você instale o Windows Server 2019 no modo Server Core, com a função de servidor de serviços Web (IIS). Um servidor no modo de Server Core é cerca de 4 GB menor que o mesmo servidor no modo de Servidor com GUI. 
> 
> A partição do sistema precisará de espaço extra em qualquer uma das seguintes circunstâncias:  
> 
> -   Se você instalar o sistema em uma rede.  
> -   Computadores com mais de 16 GB de RAM precisarão de mais espaço em disco para arquivos de paginação, hibernação e despejo.  

## <a name="network-adapter-requirements"></a>Requisitos do adaptador de rede  

Os adaptadores de rede usados com essa versão devem incluir estes recursos:  

**Mínimo**:  
- Um adaptador de Ethernet capaz de pelo menos produtividade de gigabit  
- Compatível com a especificação de arquitetura PCI Express.  

Um adaptador de rede que oferece suporte à depuração de rede (KDNet) é útil, mas não é um requisito mínimo.   

Um adaptador de rede que suporta o ambiente de execução pré-inicialização (PXE) é útil, mas não é um requisito mínimo.

## <a name="other-requirements"></a>Outros requisitos  
Os computadores que executam essa versão também devem ter o seguinte:  

-   Unidade de DVD (caso pretenda instalar o sistema operacional usando mídia de DVD)  

Os itens a seguir não são rigorosamente exigidos, mas são necessários para determinados recursos:  

- Sistema UEFI baseado em 2.3.1c e firmware que oferece suporte à inicialização segura  
- Trusted Platform Module  

-   Dispositivo gráfico e monitor capaz de Super VGA (1024 x 768) ou resolução superior  

-   Teclado e mouse Microsoft&reg; (ou outro dispositivo apontador compatível)  

-   Acesso à Internet (tarifas podem ser aplicadas)  

> [!NOTE]  
> Um chip Trusted Platform Module (TPM) não é estritamente necessário para instalar esta versão, embora seja necessário para usar determinados recursos, como Criptografia de Unidade de Disco BitLocker. Se o computador usar TPM, ele deverá atender a estes requisitos:  
>  
> - Os TPMs baseados em hardware devem implementar a versão 2.0 da especificação de TPM.  
> - Os TPMs que implementam a versão 2.0 devem ter um certificado EK previamente provisionado ao TPM pelo fornecedor de hardware ou ser capazes de serem recuperados pelo dispositivo durante a primeira inicialização.  
> - Os TPMs que implementam a versão 2.0 devem acompanhar os bancos PCR SHA-256 e implemente os PCRs 0 a 23 para SHA-256. É aceitável enviar os TPMs com um único banco de PCR de alternância que pode ser usado para as medições de SHA-1 e SHA-256.  
> - Uma opção de UEFI para desativar o TPM não é um requisito.  