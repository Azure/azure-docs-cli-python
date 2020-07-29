---
title: Azure CLI references for Azure Network
description: Azure CLI reference landing page for Azure Network
author: dbradish-microsoft
manager: barbkess
ms.devlang: azurecli
ms.topic: reference
ms.date: 06/30/2020
ms.author: dbradish
ms.service: azure-cli
ms.devlang: azurecli
ms.reviewer: mohnader
---

# Azure CLI for Azure Network

The Azure Command Line Interface ([Azure CLI](/cli/azure/what-is-azure-cli)) is a set of commands used to create and manage Azure resources.  It is available across many Azure services including Azure Network.  There are many references for networking that give you the ability to work effectively with Azure Network services from a command line.

## References for Azure Network

The [Azure Network](/azure/azure-Network/) CLI experience is composed of two parts: Azure CLI (commonly referred to as CLI **core**) and the Azure Network CLI **extension**.  An extension gives you access to experimental and pre-release commands, and must be installed prior to use.  See [Installing extension references](#installing-extension-references) for script examples.

### Virtual network

| Subgroup | Reference | Use | Is extension
|-|-|-|-|
| Appliance | [az network virtual-appliance](/cli/azure/network/virtual-appliance) | Manage Azure Network Virtual Appliance.
| DNS | [az network private-dns](/cli/azure/network/private-dns) core | Manage Private DNS domains in Azure. |
| DNS | [az network private-dns](/cli/azure/ext/privatedns/network/private-dns) extension | Manage Private DNS domains in Azure with additional parameters. | yes
| Endpoint | [az network service-endpoint](/cli/azure/network/service-endpoint) | Manage policies related to service endpoints. |
| NAT | [az network nat](/cli/azure/network/nat) | Manage network address translation resources. |
| NIC | [az network nic](/cli/azure/network/nic) | Manage network interfaces. |
| Peering | [az peering](/cli/azure/ext/peering/peering) | Manage peering. | yes
| Profile | [az network profile](/cli/azure/network/profile) | Manage network profiles. |
| Route | [az network route-filter](/cli/azure/network/route-filter) | Manage route filters. |
| Route | [az network route-table](/cli/azure/network/route-table) | Manage route tables. |
| VMware | [az network vmware](/cli/azure/ext/vmware/vmware) | Commands to manage Azure VMware Solutions. | yes
| vNet | [az network vnet](/cli/azure/network/vnet) | Manage Azure Virtual Networks. |
| vNet | [az network vnet-tap](/cli/azure/ext/virtual-network-tap/network/vnet/tap) | Manage virtual network taps. | yes
| vNet | [az network vnet-gateway](/cli/azure/network/vnet-gateway) | Use an Azure Virtual Network Gateway to establish secure, cross-premises connectivity. |

### Virtual machine

| Subgroup | Reference | Use | Is extension
|-|-|-|-|
| VM | [az vm](/cli/azure/vm) | Manage Linux or Windows virtual machines. |
| VM | [az network vm-repair](/cli/azure/ext/vm-repair/vm) | Manage Linux or Windows virtual machines. | yes
| VMSS | [az vmss](/cli/azure/vmss) | Manage groupings of virtual machines in an Azure Virtual Machine Scale Set. |
| Image | [az image](/cli/azure/image) | Manage custom virtual machine images. |
| Snapshot | [az snapshot](/cli/azure/snapshot) | Manage point-in-time copies of managed disks, native blobs, or other snapshots. |

### WAN and On-premise connectivity

| Subgroup | Reference | Use | Is extension
|-|-|-|-|
| Cross connection | [az network cross-connection](/cli/azure/ext/express-route-cross-connection/network/cross-connection) | Manage Azure Network resources. | yes
| ExpressRoute | [az network express-route](/cli/azure/network/express-route) | Manage Azure IoT hubs. |
| vHub | [az network vhub](/cli/azure/ext/virtual-wan/network/vhub) | Manage virtual hubs. | yes
| VPN | [az network vpn-connection](/cli/azure/network/vpn-connection) | Manage VPN connections. |
| VPN | [az network vpn-gateway](/cli/azure/ext/virtual-wan/network/vpn-gateway) | Manage VPN gateways. | yes
| VPN | [az network vpn-site](/cli/azure/ext/virtual-wan/network/vpn-site) | Manage VPN site configurations. | yes
| vRouter | [az network vrouter](/cli/azure/network/vrouter) | Manage the virtual router. |
| vWAN | [az network vwan](/cli/azure/ext/virtual-wan/network/vwan) | Manage virtual WANs. | yes

### Load balancing and IP

| Subgroup | Reference | Use | Is extension
|-|-|-|-|
| Application Gateway | [az network application-gateway](/cli/azure/network/application-gateway) | Manage application-level routing and load balancing services. |
| InfiniBand | [az network ib](/cli/azure/network/reference-network-ib) | Manage and configure load balancers. |
| Front Door | [az network front-door](/cli/azure/ext/frontdoor/network/front-door) | Manage networking Front Door resources. | yes
| Local Gateway | [az network local-gateway](/cli/azure/network/local-gateway) | Manage local gateways. |
| Public IP | [az network public-ip](/cli/azure/network/public-ip) | Manage public IP addresses. |
| Traffic manager | [az network traffic-manager](/cli/azure/network/traffic-manager) | Manage the routing of incoming traffic. |

### Security

| Subgroup | Reference | Use | Is extension
|-|-|-|-|
| ASG | [az asg](/cli/azure/network/asg) | Manage application security groups. |
| Bastion | [az network bastion](/cli/azure/network/bastion) | Manage Azure bastion host. |
| DDoS | [az network ddos-protection](/cli/azure/network/ddos-protection) | Manage DDoS Protection Plans. |
| Firewall | [az network firewall](/cli/azure/network/firewall) | Manage and configure Azure Firewalls. |
| Firewall | [az network security-partner-provider](/cli/azure/network/security-partner-provider) | Manage Azure security partner provider. |
| NSG | [az network nsg](/cli/azure/network/nsg)| Manage Azure Network Security Groups. |
| Private endpoint | [az network private-endpoint](/cli/azure/network/private-endpoint) | Manage private endpoints. |
| Private endpoint | [az network private-endpoint-connection](/cli/azure/network/private-endpoint-connection) | Manage private endpoint connections. |
| Private link | [az network private-link-resource](/cli/azure/network/private-link-resource) | Manage private link resources. |
| Private link | [az network private-link-service](/cli/azure/network/private-link-service) | Manage private link services. |

### Monitoring

| Subgroup | Reference | Use | Is extension
|-|-|-|-|
| Watcher | [az network watcher](/cli/azure/network/watcher) | Manage the Azure Network Watcher. |

### Azure CLI

| Subgroup | Reference | Use | Is extension
|-|-|-|-|
| Service | [az network list-service-aliases](/cli/azure/network/list-service-aliases) | List available service aliases in the region that can be used for Service Endpoint Policies. |
| Service | [az network list-service-tags](/cli/azure/nsecurity-partner-provideretwork/list-service-tags) | List all service tags that belong to different resources. |
| Usage | [az network list-usages](/cli/azure/network/list-usages) | List the number of network resources in a region that are used against a subscription quota. |

## Installing extension references

Azure CLI extension references must be installed prior to use.  The [az extension add](/cli/azure/azure-cli-extensions-overview) command installs an extension reference by name.  Learn more about extension references in [Use extensions with Azure CLI](/cli/azure/azure-cli-extensions-overview).

```azurecli
## get a list of available Azure CLI extensions
az extension list-available --output table

# install the extension for az network express-route-cross-connection
az extension add --name express-route-cross-connection

# install the extension for az network front-door
az extension add --name front-door

# install the extension for az network virtual-wan
az extension add --name virtual-wan

# install the extension for az network vm-repair
az extension add --name virtual-network-tap

# install the extension for az network vmware
az extension add --name vmware

# install the extension for az peering
az extension add --name peering

# install the extension for az private-dns
az extension add --name privatedns
```

## Popular network articles using the Azure CLI

- [Create virtual machines](/cli/azure/azure-cli-vm-tutorial)
- [Create a virtual network](/azure/virtual-network/quick-create-cli)
- [Azure CLI Samples for Windows virtual machines](/azure/virtual-machines/windows/cli-samples?toc=%2Fcli%2Fazure%2Ftoc.json&bc=%2Fcli%2Fazure%2Fbreadcrumb%2Ftoc.json)
- [Create a virtual machine scale set](/azure/virtual-machine-scale-sets/quick-create-cli)
- [Run Azure IoT Edge on Ubuntu Virtual Machines](/azure/iot-edge/how-to-install-iot-edge-ubuntuvm#deploy-from-azure-cli)
- [Load balance Linux virtual machines in Azure](/azure/virtual-machines/linux/tutorial-load-balancer)
- [Create and manage Azure virtual networks for Linux VMs](/azure/virtual-machines/linux/tutorial-virtual-network)
- [Configure a service endpoint for Cosmos DB](/azure/cosmos-db/how-to-configure-vnet-service-endpoint#configure-using-cli)

## See also

- [Get started with Azure CLI](/cli/azure/get-started-with-azure-cli) to learn about installation and sign in.

- Discover additional [released](/cli/azure/reference-index) and [extension](/cli/azure/azure-cli-extensions-list) references in the Azure CLI documentation.