# [Rede](Networking.md)
## [Cenários de rede com suporte do Windows Server](windows-server-supported-networking-scenarios.md)

## [Novidades na rede](What-s-New-in-Networking.md)

## [Diretrizes de rede principal para o Windows Server](core-network-guide/core-network-guide-windows-server.md)
### [Componentes da rede principal](core-network-guide/Core-Network-Guide.md)
### [Diretrizes complementares de rede principal](core-network-guide/cncg/Core-Network-companion-Guides.md)
#### [Implantar certificados de servidor para implantações com e sem fio do 802.1X](core-network-guide/cncg/server-certs/Deploy-Server-Certificates-for-802.1X-Wired-and-Wireless-Deployments.md)
##### [Visão geral da implantação de certificado do servidor](core-network-guide/cncg/server-certs/Server-Certificate-Deployment-Overview.md)
##### [Planejamento da implantação de certificado do servidor](core-network-guide/cncg/server-certs/Server-Certificate-Deployment-Planning.md)
##### [Implantação de certificados do servidor](core-network-guide/cncg/server-certs/Server-Certificate-Deployment.md)
###### [Instalar o servidor Web WEB1](core-network-guide/cncg/server-certs/Install-the-Web-Server-WEB1.md)
###### [Criar um registro de alias (CNAME) em DNS para WEB1](core-network-guide/cncg/server-certs/create-an-Alias-CNAME-Record-in-DNS-for-WEB1.md)
###### [Configurar WEB1 para distribuir CRLs (listas de certificados revogados)](core-network-guide/cncg/server-certs/Configure-WEB1-to-Distribute-Certificate-Revocation-lists.md)
###### [Preparar o arquivo CAPolicy.inf](core-network-guide/cncg/server-certs/Prepare-the-CAPolicy-inf-File.md)
###### [Instalar a autoridade de certificação](core-network-guide/cncg/server-certs/Install-the-Certification-Authority.md)
###### [Configurar as extensões CPD e AIA em CA1](core-network-guide/cncg/server-certs/Configure-the-cdP-and-AIA-Extensions-on-CA1.md)
###### [Copiar o certificado de Autoridade de Certificação e CRL para o diretório virtual](core-network-guide/cncg/server-certs/copy-the-CA-Certificate-and-CRL-to-the-Virtual-directory.md)
###### [Configurar o modelo de certificado do servidor](core-network-guide/cncg/server-certs/Configure-the-Server-Certificate-Template.md)
###### [Configurar o registro automático de certificados do servidor](core-network-guide/cncg/server-certs/Configure-Server-Certificate-Autoenrollment.md)
###### [Atualizar política de grupo](core-network-guide/cncg/server-certs/Refresh-Group-Policy.md)
###### [Verificar registro de servidor de um certificado do servidor](core-network-guide/cncg/server-certs/verify-Server-Enrollment-of-a-Server-Certificate.md)
#### [Implantar acesso sem fio autenticado 802.1X baseado em senha](core-network-guide/cncg/wireless/a-deploy-8021X-wireless-access.md)
##### [Visão geral da implantação de acesso sem fio](core-network-guide/cncg/wireless/b-wireless-access-deploy-overview.md)
##### [Processo da implantação de acesso sem fio](core-network-guide/cncg/wireless/c-wireless-access-deploy-process.md)
##### [Planejamento da implantação de acesso sem fio](core-network-guide/cncg/wireless/d-wireless-access-planning.md)
##### [Implantação de acesso sem fio](core-network-guide/cncg/wireless/e-wireless-access-deployment.md)
#### [Implantar o modo de cache hospedado do BranchCache](core-network-guide/cncg/bc-hcm/1-Deploy-Bc-Hcm.md)
##### [Visão geral da implantação do modo de cache hospedado do BranchCache](core-network-guide/cncg/bc-hcm/2-Bc-Hcm-Deploy-Overview.md)
##### [Planejamento da implantação do modo de cache hospedado do BranchCache](core-network-guide/cncg/bc-hcm/3-Bc-Hcm-Plan.md)
##### [Implantação do modo de cache hospedado do BranchCache](core-network-guide/cncg/bc-hcm/4-Bc-Hcm-Deployment.md)
###### [Instalar o recurso BranchCache e configurar o servidor de cache hospedado por ponto de conexão de serviço](core-network-guide/cncg/bc-hcm/5-Bc-Feature-Scp.md)
###### [Mover e redimensionar o cache hospedado (opcional)](core-network-guide/cncg/bc-hcm/6-Bc-move-Resize-Cache.md)
###### [Realizar hash prévio e pré-carregar conteúdo no servidor de cache hospedado (opcional)](core-network-guide/cncg/bc-hcm/7-Bc-Prehash-Preload.md)
####### [Criar pacotes de dados do servidor de conteúdo para conteúdo da Web e do arquivo (opcional)](core-network-guide/cncg/bc-hcm/8-Bc-Data-Packages.md)
####### [Importar pacotes de dados no servidor de cache hospedado (opcional)](core-network-guide/cncg/bc-hcm/9-Bc-import-Data.md)
###### [Configurar descoberta automática de cache hospedado cliente por ponto de conexão de serviço](core-network-guide/cncg/bc-hcm/10-Bc-Client-By-Scp.md)
##### [Recursos adicionais](core-network-guide/cncg/bc-hcm/11-Bc-Hcm-additional-resources.md)

## [BranchCache](branchcache/BranchCache.md)
### [Netsh BranchCache e comandos do Windows PowerShell](branchcache/BranchCache-Network-Shell-and-Windows-powershell-Commands.md)
### [Guia de implantação do BranchCache](branchcache/deploy/BranchCache-Deployment-Guide.md)
#### [Escolher um design para o BranchCache](branchcache/plan/Choosing-a-BranchCache-Design.md)
#### [Implantar o BranchCache](branchcache/deploy/Deploy-BranchCache.md)
##### [Instalar e configurar servidores de conteúdo](branchcache/deploy/Install-and-Configure-Content-Servers.md)
###### [Instalar servidores de conteúdo que usam o recurso BranchCache](branchcache/deploy/Install-Content-Servers-that-Use-the-BranchCache-Feature.md)
####### [Instalar o recurso BranchCache](branchcache/deploy/Install-the-BranchCache-Feature.md)
####### [Configurar servidores de conteúdo do WSUS (Windows Server Update Services)](branchcache/deploy/configure-wsus-content-servers.md)
###### [Instalar servidores de conteúdo dos Serviços de Arquivo](branchcache/deploy/Install-File-Services-Content-Servers.md)
####### [Configurar a função de servidor de Serviços de Arquivo](branchcache/deploy/Configure-the-File-Services-server-role.md)
######## [Instalar um novo servidor de arquivos como um servidor de conteúdo](branchcache/deploy/Install-a-New-File-Server-as-a-Content-Server.md)
######## [Configurar um servidor de arquivos existente como servidor de conteúdo](branchcache/deploy/Configure-an-Existing-File-Server-as-a-Content-Server.md)
####### [Habilitar publicação de hash para servidores de arquivos](branchcache/deploy/Enable-Hash-Publication-for-File-Servers.md)
######## [Habilitar a publicação de hash para servidores de arquivos que não são membros do domínio](branchcache/deploy/Enable-Hash-Publication-for-Non-Domain-Member-File-Servers.md)
######## [Habilitar a publicação de hash para servidores de arquivos membros do domínio](branchcache/deploy/Enable-Hash-Publication-for-Domain-Member-File-Servers.md)
######### [Criar a UO (unidade organizacional) de servidores de arquivos BranchCache](branchcache/deploy/create-the-BranchCache-File-Servers-Organizational-Unit.md)
######### [Mover servidores de arquivos para UO dos servidores de arquivos BranchCache](branchcache/deploy/move-File-Servers-to-the-BranchCache-File-Servers-Organizational-Unit.md)
######### [Criar objeto de política de grupo (GPO) da publicação de hash BranchCache](branchcache/deploy/create-the-BranchCache-Hash-Publication-Group-Policy-Object.md)
######### [Configurar GPO da publicação de hash BranchCache](branchcache/deploy/Configure-the-BranchCache-Hash-Publication-Group-Policy-Object.md)
####### [Habilitar BranchCache em um compartilhamento de arquivo (opcional)](branchcache/deploy/enable-bc-on-file-share.md)
##### [Implantar servidores de cache hospedado (opcional)](branchcache/deploy/deploy-hosted-cache-servers.md)
##### [Realizar o hash prévio e o pré-carregamento de conteúdo em servidores de cache hospedado (opcionais)](branchcache/deploy/prehashing-and-preloading.md)
##### [Configurar BranchCache em computadores cliente](branchcache/deploy/Configure-BranchCache-Client-computers.md)
###### [Usar política de grupo para configurar computadores cliente do membro do domínio](branchcache/deploy/Use-Group-Policy-to-Configure-Domain-Member-Client-computers.md)
###### [Usar o Windows PowerShell para configurar computadores cliente do membro que não sejam de domínio](branchcache/deploy/Use-Windows-powershell-to-Configure-Non-Domain-Member-Client-computers.md)
####### [Configurar regras de firewall para membros não associados a domínio para permitir tráfego BranchCache](branchcache/deploy/Configure-Firewall-Rules-for-Non-Domain-Members-to-Allow-BranchCache-Traffic.md)
###### [Verificar configurações do computador cliente](branchcache/deploy/verify-Client-computer-Settings.md)

## [DirectAccess](../remote/remote-access/da-stub.md) 

## [Sistema de nome de domínio (DNS)](dns/dns-top.md)
### [Novidades no cliente DNS no Windows Server](dns/What-s-New-in-DNS-Client.md)
### [Novidades no servidor DNS no Windows Server](dns/What-s-New-in-DNS-Server.md)
### [Diretrizes de cenário de política DNS](dns/deploy/DNS-Policy-Scenario-Guide.md)
#### [Visão geral das políticas de DNS](dns/deploy/DNS-Policies-Overview.md)
#### [Usar a política DNS para gerenciamento de tráfego de localização geográfica com servidores primários](dns/deploy/primary-geo-location.md)
#### [Usar a política DNS para gerenciamento de tráfego de localização geográfica com implantações primárias e secundárias](dns/deploy/primary-secondary-geo-location.md)
#### [Usar a política DNS para respostas DNS inteligentes com base na hora do dia](dns/deploy/dns-tod-intelligent.md)
#### [Respostas de DNS com base na hora do dia com o Servidor de aplicativos da nuvem do Azure](dns/deploy/dns-tod-azure-cloud-app-server.md)
#### [Usar a política DNS para a implantação de DNS com partição de rede](dns/deploy/split-brain-DNS-deployment.md)
#### [Usar a política DNS para a DNS com partição de rede no Active Directory](dns/deploy/dns-sb-with-ad.md)
#### [Usar a política DNS para a aplicação de filtros em consultas DNS](dns/deploy/apply-filters-on-dns-queries.md)
#### [Usar a política DNS para balanceamento de carga do aplicativo](dns/deploy/app-lb.md)
#### [Usar a política DNS para balanceamento de carga de aplicativo com reconhecimento de localização geográfica](dns/deploy/app-lb-geo.md)

## [Protocolo DHCP](technologies/dhcp/dhcp-top.md)
### [Novidades no DHCP](technologies/dhcp/What-s-New-in-DHCP.md)
#### [Opções de seleção de sub-rede DHCP](technologies/dhcp/dhcp-subnet-options.md)
#### [Eventos de registro em log de DHCP para registros de DNS](technologies/dhcp/dhcp-dns-events.md)
### [Implantar o DHCP usando o Windows PowerShell](technologies/dhcp/dhcp-deploy-wps.md)

## [HPN (rede de alto desempenho)](technologies/hpn/hpn-top.md)
### [Tecnologias de descarregamento e de otimização de rede](technologies/hpn/network-offload-and-optimization.md)
#### [Recursos e tecnologias de SO (apenas software)](technologies/hpn/hpn-software-only-features.md)
#### [Recursos e tecnologias integrados a SH (software e hardware)](technologies/hpn/hpn-software-hardware-features.md)
#### [Tecnologias e recursos de HO (apenas hardware)](technologies/hpn/hpn-hardware-only-features.md)
#### [Propriedades avançadas de NIC](technologies/hpn/hpn-nic-advanced-properties.md)

### [Insider Preview](technologies/hpn/hpn-insider-preview.md)
### [RSC (União de Segmentos de Recebimento) no vSwitch](technologies/hpn/rsc-in-the-vswitch.md)

### [Diretrizes de configuração de NIC convergida](technologies/conv-nic/cnic-top.md)
#### [Configuração do adaptador de rede único](technologies/conv-nic/cnic-single.md)
#### [Configuração de adaptador de rede do datacenter](technologies/conv-nic/cnic-datacenter.md)
#### [Configuração do comutador físico](technologies/conv-nic/cnic-app-switch-config.md)
#### [Solução de problemas de NIC convergente](technologies/conv-nic/cnic-app-troubleshoot.md)

### [DCB \(Data Center Bridging\)](technologies/dcb/dcb-top.md)
#### [Instalar DCB](technologies/dcb/dcb-install.md)
#### [Gerenciar DCB](technologies/dcb/dcb-manage.md)

### [vRSS (Virtual Receive Side Scaling)](technologies/vrss/vrss-top.md)
#### [Planejar o uso de vRSS](technologies/vrss/vrss-plan.md)
#### [Habilitar vRSS em um adaptador de rede virtual](technologies/vrss/vrss-enable.md)
#### [Gerenciar vRSS](technologies/vrss/vrss-manage.md)
#### [Perguntas frequentes sobre vRSS](technologies/vrss/vrss-faq.md)
#### [Comandos do Windows PowerShell para RSS e vRSS](technologies/vrss/vrss-wps.md)
#### [Resolver problemas de vRSS](technologies/vrss/vrss-resolve-issues.md)

## [API de serviço de HCN (rede de computação de host)](technologies/hcn/hcn-top.md)   
### [Cenários comuns de HCN](technologies/hcn/hcn-scenarios.md)
### [Identificadores de contexto de RPC para HCN](technologies/hcn/hcn-declaration-handles.md)
### [Esquemas de documento JSON de HCN](technologies/hcn/hcn-json-document-schemas.md)
### [Exemplo de código gerado por C#](technologies/hcn/example-c-sharp.md)
### [Exemplo de código gerado por Go](technologies/hcn/example-go.md)

## [Comutador Virtual do Hyper-V](technologies/vswitch-stub.md)

## [IPAM (Gerenciamento de Endereço IP)](technologies/ipam/ipam-top.md)
### [Novidades no IPAM](technologies/ipam/What-s-New-in-IPAM.md)
### [Gerenciar IPAM](technologies/ipam/Manage-IPAM.md)
#### [Gerenciamento de registro de recursos de DNS](technologies/ipam/DNS-Resource-Record-Management.md)
##### [Adicionar um registro de recursos de DNS](technologies/ipam/add-a-DNS-Resource-Record.md)
##### [Excluir registros de recursos de DNS](technologies/ipam/delete-DNS-Resource-Records.md)
##### [Filtrar a exibição de registros de recursos de DNS](technologies/ipam/Filter-the-View-of-DNS-Resource-Records.md)
##### [Exibir registros de recurso de DNS para um endereço IP específico](technologies/ipam/View-DNS-Resource-Records-for-a-Specific-IP-address.md)
#### [Gerenciamento de zonas DNS](technologies/ipam/DNS-Zone-Management.md)
##### [Criar uma zona DNS](technologies/ipam/create-a-DNS-Zone.md)
##### [Editar uma zona DNS](technologies/ipam/edit-a-DNS-Zone.md)
##### [Exibir registros de recurso de DNS para uma zona DNS](technologies/ipam/View-DNS-Resource-Records-for-a-DNS-Zone.md)
##### [Exibir zonas DNS](technologies/ipam/View-DNS-Zones.md)
#### [Gerenciar recursos em várias florestas do Active Directory](technologies/ipam/Manage-Resources-in-Multiple-active-directory-forests.md)
#### [Limpar dados de utilização](technologies/ipam/Purge-Utilization-Data.md)
#### [Controle de acesso baseado em função](technologies/ipam/Role-based-Access-Control.md)
##### [Gerenciar controle de acesso baseado em função com o Gerenciador do Servidor](technologies/ipam/Manage-Role-Based-Access-Control-with-server-manager.md)
###### [Criar uma função de usuário para controle de acesso](technologies/ipam/create-a-User-Role-for-Access-Control.md)
###### [Criar uma política de acesso](technologies/ipam/create-an-Access-Policy.md)
###### [Definir escopo de acesso para uma zona DNS](technologies/ipam/Set-Access-Scope-for-a-DNS-Zone.md)
###### [Definir escopo de acesso para registros de recurso DNS](technologies/ipam/Set-Access-Scope-for-DNS-Resource-Records.md)
###### [Exibir funções e permissões de função](technologies/ipam/View-Roles-and-Role-Permissions.md)
##### [Gerenciar controle de acesso baseado em função com o Windows PowerShell](technologies/ipam/Manage-Role-Based-Access-Control-with-Windows-powershell.md)

## [Balanceamento de Carga de Rede](technologies/Network-Load-Balancing.md)



## [NPS (Servidor de Políticas de Rede)](technologies/nps/nps-top.md)
### [Melhores práticas do NPS](technologies/nps/nps-best-practices.md)
### [Introdução ao NPS](technologies/nps/nps-getstart-top.md)
#### [Processamento de solicitações de conexão](technologies/nps/nps-crp-top.md)
##### [Políticas de solicitação de conexão](technologies/nps/nps-crp-crpolicies.md)
##### [Nomes de realm](technologies/nps/nps-crp-realm-names.md)
##### [Grupos de servidores RADIUS remotos](technologies/nps/nps-crp-rrsg.md)
#### [Políticas de rede](technologies/nps/nps-np-overview.md)
##### [Permissão de acesso](technologies/nps/nps-np-access.md)
#### [Modelos NPS](technologies/nps/nps-templates.md)
#### [Clientes RADIUS](technologies/nps/nps-radius-clients.md)
### [Planejar o NPS](technologies/nps/nps-plan-top.md)
#### [Planejar NPS como um servidor RADIUS](technologies/nps/nps-plan-server.md)
#### [Planejar NPS como um proxy RADIUS](technologies/nps/nps-plan-proxy.md)
### [Implantar o NPS](technologies/nps/nps-deploy.md)
### [Gerenciar NPS](technologies/nps/nps-manage-top.md)
#### [Gerenciamento de Servidor de Políticas de Rede com Ferramentas de Administração](technologies/nps/nps-admintools.md)
#### [Configurar políticas de solicitação de conexão](technologies/nps/nps-crp-configure.md)
#### [Configurar firewalls para tráfego RADIUS](technologies/nps/nps-firewalls-configure.md)
#### [Configurar políticas de rede](technologies/nps/nps-np-configure.md)
#### [Configurar a contabilização do NPS](technologies/nps/nps-accounting-configure.md)
#### [Configurar clientes RADIUS](technologies/nps/nps-radius-clients-configure.md)
#### [Configurar grupos de servidores RADIUS remotos](technologies/nps/nps-crp-rrsg-configure.md)
#### [Gerenciar certificados usados com NPS](technologies/nps/nps-manage-certificates.md)
##### [Configurar modelos de certificado para requisitos de PEAP e EAP](technologies/nps/nps-manage-cert-requirements.md)
#### [Gerenciar NPSs](technologies/nps/nps-manage-servers.md)
##### [Configurar o NPS em um computador multihomed](technologies/nps/nps-multihomed-configure.md)
##### [Configurar informações da porta UDP do NPS](technologies/nps/nps-udp-ports-configure.md)
##### [Desabilitar o encaminhamento de notificações do NAS](technologies/nps/nps-disable-nas-notifications.md)
##### [Exportar uma configuração do NPS para importar em outro servidor](technologies/nps/nps-manage-export.md)
##### [Aumentar autenticações simultâneas processadas pelo NPS](technologies/nps/nps-concurrent-auth.md)
##### [Instalar o NPS](technologies/nps/nps-manage-install.md)
##### [Balanceamento de carga do servidor proxy NPS](technologies/nps/nps-manage-proxy-lb.md)
##### [Registrar um NPS em um domínio do Active Directory](technologies/nps/nps-manage-register.md)
##### [Cancelar o registro de um NPS de um domínio do Active Directory](technologies/nps/nps-manage-unregister.md)
##### [Use expressões regulares no NPS](technologies/nps/nps-crp-reg-expressions.md)
##### [Verificar configuração depois das alterações do NPS](technologies/nps/nps-manage-verify.md)
##### [Coleta de dados do NPS](technologies/nps/nps-data-collection.md)
#### [Gerenciar modelos do NPS](technologies/nps/nps-manage-templates.md)

## [Shell de Rede (Netsh)](technologies/netsh/netsh.md)
### [Sintaxe, contextos e formatação do comando netsh](technologies/netsh/netsh-contexts.md)
### [Arquivo de lote de exemplo de Shell (Netsh) de rede](technologies/netsh/netsh-wins.md)
### [Comandos Netsh http](technologies/netsh/netsh-http.md)
### [Comandos netsh interface portproxy](technologies/netsh/netsh-interface-portproxy.md)

## [Ajuste de desempenho do subsistema de rede](technologies/network-subsystem/net-sub-performance-top.md)
### [Como escolher um adaptador de rede](technologies/network-subsystem/net-sub-choose-nic.md)
### [Configurar a ordem das interfaces de rede](technologies/network-subsystem/net-sub-interface-metric.md)
### [Adaptadores de rede de ajuste de desempenho](technologies/network-subsystem/net-sub-performance-tuning-nics.md)
### [Contadores de desempenho relacionados à rede](technologies/network-subsystem/net-sub-performance-counters.md)
### [Ferramentas de desempenho para cargas de trabalho de rede](technologies/network-subsystem/net-sub-performance-tools.md)

## [Agrupamento NIC](technologies/nic-teaming/NIC-Teaming.md)
### [Gerenciamento e uso do endereço MAC de agrupamento NIC](technologies/nic-teaming/NIC-Teaming-MAC-address-Use-and-Management.md)
### [Criar um agrupamento NIC em uma VM ou computador host](technologies/nic-teaming/create-a-New-NIC-Team-on-a-Host-computer-or-VM.md)
### [Como solucionar problemas de agrupamento NIC](technologies/nic-teaming/Troubleshooting-NIC-Teaming.md)

## [Política de QoS (qualidade de serviço)](technologies/qos/qos-policy-top.md)
### [Introdução à política de QoS](technologies/qos/qos-policy-get-started.md)
#### [Como funciona a política de QoS](technologies/qos/qos-policy-works.md)
#### [Arquitetura de política de QoS](technologies/qos/qos-policy-architecture.md)
#### [Cenários de política de QoS](technologies/qos/qos-policy-scenarios.md)
###[Gerenciar a política de QoS](technologies/qos/qos-policy-manage.md)
#### [Erros e eventos de política de QoS](technologies/qos/qos-policy-errors.md)
### [Perguntas frequentes sobre a política de QoS](technologies/qos/qos-policy-faq.md)

## [SDN (rede definida pelo software)](sdn/index.yml)

### [Visão geral da SDN no Windows Server](sdn/software-defined-networking.md)

### [Tecnologias da SDN](sdn/technologies/Software-Defined-Networking-Technologies.md)
#### [Virtualização de rede Hyper-V](sdn/technologies/hyper-v-network-virtualization/Hyper-V-Network-Virtualization.md)
##### [Visão geral da virtualização de rede Hyper-V](sdn/technologies/hyper-v-network-virtualization/hyperv-network-virtualization-overview-windows-server.md)
##### [Detalhes técnicos da virtualização de rede Hyper-V](sdn/technologies/hyper-v-network-virtualization/hyperv-network-virtualization-technical-details-windows-server.md)
##### [Novidades na virtualização de rede Hyper-V](sdn/technologies/hyper-v-network-virtualization/whats-new-hyperv-network-virtualization-windows-server.md)
#### [iDNS (serviço DNS interno) para SDN](sdn/technologies/Idns-for-Sdn.md)
#### [Controlador de rede](sdn/technologies/network-controller/Network-Controller.md)
##### [Alta disponibilidade do controlador de rede](sdn/technologies/network-controller/network-controller-high-availability.md)
##### [Instalar a função de servidor do Controlador de Rede usando o Gerenciador do Servidor](sdn/technologies/network-controller/Install-the-Network-Controller-server-role-using-server-manager.md)
##### [Etapas de pós-implantação para controlador de rede](sdn/technologies/network-controller/post-deploy-steps-nc.md)
#### [Virtualização de função de rede](sdn/technologies/network-function-virtualization/Network-Function-Virtualization.md)
##### [Visão geral do firewall do datacenter](sdn/technologies/network-function-virtualization/Datacenter-Firewall-Overview.md)
##### [Gateway de RAS para SDN](sdn/technologies/network-function-virtualization/RAS-Gateway-for-SDN.md)
###### [Novidades no Gateway de RAS](sdn/technologies/network-function-virtualization/What-s-New-in-RAS-Gateway.md)
###### [Arquitetura de implantação do Gateway de RAS](sdn/technologies/network-function-virtualization/RAS-Gateway-Deployment-Architecture.md)
###### [Alta disponibilidade do Gateway de RAS](sdn/technologies/network-function-virtualization/RAS-Gateway-High-Availability.md)
##### [SLB (balanceamento de carga do software) para SDN](sdn/technologies/network-function-virtualization/software-load-balancing-for-sdn.md)
#### [SET (Agrupamento Incorporado de Comutador) para SDN](sdn/technologies/Set-for-Sdn.md)
#### [Rede de contêiner](sdn/technologies/Containers/Container-networking-overview.md)

### [Planejar SDN](sdn/plan/Plan-a-Software-Defined-Network-Infrastructure.md)
#### [Requisitos para instalação e preparação para implantação do controlador de rede](sdn/plan/Installation-and-Preparation-Requirements-for-Deploying-Network-Controller.md)

### [Implantar a SDN](sdn/deploy/Deploy-Software-Defined-Networking.md)
#### [Implantar uma infraestrutura SDN](sdn/deploy/Deploy-a-Software-Defined-Network-Infrastructure.md)
##### [Implantar uma infraestrutura SDN usando scripts](sdn/deploy/Deploy-a-Software-Defined-Network-infrastructure-using-scripts.md)
#### [Implantar tecnologias SDN usando o Windows PowerShell](sdn/deploy/Deploy-Software-Defined-Network-Technologies-using-Windows-powershell.md)
##### [Implantar controlador de rede usando o Windows PowerShell](sdn/deploy/Deploy-Network-Controller-using-Windows-powershell.md)

### [Gerenciar SDN](sdn/manage/manage-sdn.md)
#### [Gerenciar redes virtuais de locatário](sdn/manage/Manage-Tenant-Virtual-Networks.md)
##### [Noções básicas sobre o uso de redes virtuais e VLANs](sdn/manage/Understanding-Usage-of-Virtual-Networks-and-VLANs.md)
##### [Usar ACLs (listas de controle de acesso) para gerenciar o fluxo de tráfego de rede do datacenter](sdn/manage/use-acls-for-traffic-flow.md)
##### [Criar, excluir ou atualizar redes virtuais de locatário](sdn/manage/create,-delete,-or-Update-Tenant-Virtual-Networks.md)
##### [Adicionar um gateway virtual a uma rede virtual de locatário](sdn/manage/add-a-Virtual-Gateway-to-a-Tenant-Virtual-Network.md)
##### [Conectar pontos de extremidade do contêiner a uma rede virtual do locatário](sdn/manage/Connect-container-endpoints-to-a-Tenant-Virtual-Network.md)
##### [Configurar a criptografia para uma sub-rede virtual](sdn/vnet-encryption/sdn-config-vnet-encryption.md)
##### [Medição de saída em uma rede virtual](sdn/manage/sdn-egress.md)

#### [Gerenciar cargas de trabalho de locatário](sdn/manage/Manage-Tenant-Workloads.md)
##### [Criar uma VM e conectar-se a uma rede virtual de locatário ou VLAN](sdn/manage/create-a-Tenant-VM.md)
##### [Configurar a QoS para um adaptador de rede de VMs do locatário](sdn/manage/Configure-QoS-for-Tenant-VM-Network-Adapter.md)
##### [Configurar ACLs de firewall do datacenter](sdn/manage/Configure-Datacenter-Firewall-Acls.md)
##### [Configurar o balanceador de carga de software para balanceamento de carga e NAT (conversão de endereços de rede)](sdn/manage/Configure-SLB-and-Nat.md)
##### [Usar solução de virtualização de rede em uma rede virtual](sdn/manage/Use-Network-Virtual-Appliances-on-a-VN.md)
##### [Clustering convidado em uma rede virtual](sdn/manage/guest-clustering.md)
#### [Atualizar, fazer backup e restaurar uma infraestrutura SDN](sdn/manage/Update-Backup-Restore.md)

### [Segurança para SDN](sdn/security/sdn-security-top.md)
#### [Proteger o controlador de rede](sdn/security/nc-security.md)
#### [Gerenciar certificados para SDN](sdn/security/sdn-manage-certs.md)
#### [Kerberos com SPN (nome da entidade de serviço)](sdn/security/kerberos-with-spn.md)
#### [Auditoria de firewall SDN](sdn/security/sdn-firewall-auditing.md)

### [Emparelhamento de rede virtual](sdn/vnet-peering/sdn-vnet-peering.md)
#### [Configurar o emparelhamento de rede virtual](sdn/vnet-peering/sdn-configure-vnet-peering.md)

### [Desempenho de gateway do Windows Server 2019](sdn/gateway-performance.md)
### [Alocação de largura de banda de gateway](sdn/gateway-allocation.md)

### [Solucionar problemas de SDN](sdn/troubleshoot/Troubleshoot-Software-Defined-Networking.md)
#### [Solucionar problemas de pilha de rede definida pelo software do Windows Server](sdn/troubleshoot/troubleshoot-windows-server-software-defined-networking-stack.md)

### [Tecnologias do System Center para SDN](sdn/Sc-Tech-for-Sdn.md)
### [Microsoft Azure e SDN](sdn/Azure_and_Sdn.md)
### [Contatar a equipe de rede na nuvem e datacenter](sdn/contact-sdn-team.md)

## [VPN (rede virtual privada)](technologies/vpn-stub.md)

## [WINS (Serviço de Cadastramento na Internet do Windows)](technologies/wins/wins-top.md)

## [Serviço de Tempo do Windows](windows-time-service/windows-time-service-top.md)
### [Insider Preview – Serviço de Data/Hora do Windows no Windows Server 2019](windows-time-service/insider-preview.md)
### [Hora precisa do Windows Server 2016](windows-time-service/accurate-time.md)
### [Limite de suporte para hora de alta precisão](windows-time-service/support-boundary.md)
### [Como configurar sistemas de alta precisão](windows-time-service/configuring-systems-for-high-accuracy.md)
### [Horário do Windows para rastreamento](windows-time-service/windows-time-for-traceability.md)
### [Referência técnica do serviço de data/hora do Windows](windows-time-service/windows-time-service-tech-ref.md)
#### [Como o Serviço de data/hora do Windows Funciona](windows-time-service/How-the-Windows-Time-Service-Works.md)
#### [Ferramentas e configurações do Serviço de data/hora do Windows](windows-time-service/Windows-Time-Service-Tools-and-Settings.md)
