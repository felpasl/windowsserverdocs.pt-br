---
title: Solução de problemas do DirectAccess
description: Este tópico fornece informações sobre como solucionar problemas de implantações do DirectAccess no Windows Server 2016.
manager: brianlic
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.technology: networking-da
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 61040e19-5960-4eb0-b612-d710627988f7
ms.author: pashort
author: shortpatti
ms.openlocfilehash: 3ee1eb6f9855174357242d2689567b394b75aed1
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71394469"
---
# <a name="troubleshooting-directaccess"></a>Solução de problemas do DirectAccess

>Aplica-se a: Windows Server (Canal Semestral), Windows Server 2016

Siga estas etapas para solucionar problemas de acesso remoto (DirectAccess).  
  
|||  
|-|-|  
|**Problema**|**Resolução**|  
|O console de gerenciamento de acesso remoto não pode mostrar a configuração do DirectAccess|**Para restaurar as informações de configuração ausentes**<br />-Se você estiver solucionando problemas de implantação multissite, verifique se o controlador de domínio mais próximo do ponto de entrada está disponível.<br />-Use o cmdlet **Get-DAEntrypointDC** para recuperar o nome do controlador de domínio mais próximo do ponto de entrada. Se o controlador de domínio não estiver em execução, use o cmdlet **set-DAEntryPointDC** para apontar para outro controlador de domínio.<br />-Execute o **GPResult** em um prompt de comando elevado no servidor para garantir que o servidor esteja obtendo os objetos de política de grupo do DirectAccess.<br />– Habilitar o log da interface do usuário (IU).<br />-Use o seguinte comando para iniciar o log do Windows PowerShell:<pre>logman create trace ETWTrace -ow -o c:\ETWTrace.etl -p {AAD4C46D-56DE-4F98-BDA2-B5EAEBDD2B04} 0xffffffffffffffff 0xff -nb 16 16 -bs 1024 -mode 0x2 -max 2048 -ets <br />logman update trace ETWTrace -p {62DFF3DA-7513-4FCA-BC73-25B111FBB1DB} 0xffffffffffffffff 0xff -ets</pre><repro>-fechar e reabrir a interface do usuário.<br />-Desabilitar log do Windows PowerShell. Colete os arquivos de log de rastreamento de eventos. Além disso, colete todos os logs da pasta **% windir%/Tracing**|  
|A aplicação da configuração do DirectAccess falha|**Para atualizar a configuração do DirectAccess**<br />-Se você estiver solucionando problemas de implantação multissite, verifique se o controlador de domínio mais próximo do ponto de entrada está disponível.<br />-Use o cmdlet **Get-DAEntrypointDC** para recuperar o nome do controlador de domínio mais próximo do ponto de entrada. Se o controlador de domínio não estiver em execução, use o cmdlet **set-DAEntryPointDC** para apontar para outro controlador de domínio.<br />-Use o seguinte comando para iniciar o log do Windows PowerShell:<br /><pre>logman create trace ETWTrace -ow -o c:\ETWTrace.etl -p {AAD4C46D-56DE-4F98-BDA2-B5EAEBDD2B04} 0xffffffffffffffff 0xff -nb 16 16 -bs 1024 -mode 0x2 -max 2048 -ets<br />logman update trace ETWTrace -p {62DFF3DA-7513-4FCA-BC73-25B111FBB1DB} 0xffffffffffffffff 0xff -ets</pre>    <repro><br />-Clique em **aplicar**.<br />-Após a falha ocorrer, desabilite o log do Windows PowerShell e colete o log de rastreamento de eventos.|  
|O DirectAccess está configurado, mas os clientes não conseguem se conectar a recursos internos|**Para solucionar problemas de conexão do cliente**<br />-Clique na guia **status de operações** no console de gerenciamento de acesso remoto e verifique se todos os componentes mostram um ícone verde. Caso contrário, verifique os detalhes do erro e siga as etapas de resolução.<br />-Execute o Analisador de Práticas Recomendadas do servidor de acesso remoto (BPA). Se houver avisos ou erros, siga as etapas de resolução para resolver o problema.|  
|Encontrando problemas relacionados a uma configuração multissite (por exemplo, habilitando um multissite, adicionando pontos de entrada ou configurando o controlador de domínio para um ponto de entrada)|Siga as etapas em [solucionar problemas de implantação multissite](https://technet.microsoft.com/library/jj554657(v=ws.11).aspx).|  
|O bloco status da configuração no painel mostra um aviso ou erro|Siga as etapas em [monitorar o status de distribuição da configuração do servidor de acesso remoto](https://technet.microsoft.com/library/jj574221(v=ws.11).aspx).|  
|Encontrando problemas relacionados à configuração do balanceamento de carga (por exemplo, a configuração falha quando você habilita o balanceamento de carga ou há problemas ao adicionar ou remover servidores de um cluster)|Se você estivesse habilitando o balanceamento de carga ou adicionando um nó, e a configuração for atualizada quando você clicou em **aplicar**, mas o cluster não tiver formado corretamente no servidor, execute o seguinte comando: **cmd. exe/c "reg Add HKLM\SYSTEM\CurrentControlSet\ Services\RaMgmtSvc\Parameters/f/v sinalizador/t REG_DWORD/d "" 0xFFFFFFFF "" "** para coletar os logs da interface do usuário no novo servidor.|  
|Status de operações mostra um erro ou aviso após as etapas a seguir para corrigir a situação|Se o status das operações estiver mostrando informações incorretas (como erros-mesmo depois de corrigi-las):<br /><br />– Habilite a chave do registro **cmd. exe/c "reg Add HKLM\SYSTEM\CurrentControlSet\Services\RaMgmtSvc\Parameters/f/V EnableTracing/T REG_DWORD//d" "5" ""** .<br />-Atualize o status de operações e colete os logs de **% windir%/Tracing**.|  
|Os computadores cliente do Windows 8 e posteriores do DirectAccess reportam "sem Internet" como status da conexão do DirectAccess e o indicador de status de conectividade de rede (NCSI) relata conectividade limitada.|Isso pode ocorrer quando o túnel forçado está habilitado na configuração do DirectAccess e, por isso, somente o IPHTTPS está sendo usado. Para resolver esse problema, você pode criar e configurar um servidor proxy. Em seguida, o NCSI usa o servidor proxy para realizar verificações de conectividade com a Internet. É recomendável que você adicione um proxy estático para o Tabela de Políticas de Resolução de Nomes (NRPT) usando o procedimento a seguir.<br /><br />Antes de executar os comandos neste procedimento, certifique-se de substituir todos os nomes de domínio, nomes de computador e outras variáveis de comando do Windows PowerShell por valores apropriados para sua implantação.<br /><br />**Configurar um proxy estático para uma regra NRPT**<br />1.  Exibir o "." Regra NRPT: `Get-DnsClientNrptRule -GpoName "corp.example.com\DirectAccess Client Settings" -Server <DomainControllerNetBIOSName>`<br />2.  Observe o nome (GUID) do "." Regra NRPT. O nome (GUID) deve começar com o **da-{..}**<br />3.  Defina o proxy para o "." Regra NRPT para **proxy.Corp.example.com:8080**: `Set-DnsClientNrptRule -Name "DA-{..}" -Server <DomainControllerNetBIOSName> -GPOName "corp.example.com\DirectAccess Client Settings" -DAProxyServerName "proxy.corp.example.com:8080" -DAProxyType "UseProxyName"`<br />4.  Exibir o "." Regra NRPT novamente executando `Get-DnsClientNrptRule` e verifique se **ProxyFQDN: Port** está configurado corretamente.<br />5.  Atualize Política de Grupo executando `gpupdate /force` em um cliente do DirectAccess quando o cliente estiver conectado internamente e, em seguida, exiba o NRPT usando `Get-DnsClientNrptPolicy` e verifique se a regra "." mostra **ProxyFQDN: Port**.|  
  


