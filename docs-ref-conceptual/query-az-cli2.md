---
title: Query command results with Azure CLI 2.0
description: Use --query to perform JMESPath queries on the output of Azure CLI 2.0 commands.
keywords: Azure CLI 2.0, JMESPath, query, Linux, Mac, Windows, OS X
author: allclark
manager: douge
ms.date: 02/18/2017
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.assetid: 5979acc5-21a5-41e2-a4b6-3183bfe6aa22
---

# Query with Azure CLI 2.0

Use the `--query` parameter to execute a [JMESPath query](http://jmespath.org) output format results of your `az` command to customize the properies and values you want to see. JMESPATH is a powerful query language for JSON outputs.

For example, the following lists the Resource Group and VM names for all Virtual Machines in your subscription.

```azurecli
az vm list \
  --query [*].[name,resourceGroup]
```

```json
Column1    Column2
---------  -----------
DEMORG1    DemoVM010
DEMORG1    demovm111
DEMORG1    demovm211
DEMORG1    demovm212
DEMORG1    demovm213
DEMORG1    demovm214
DEMORG1    demovm222
RGDEMO001  KBDemo001VM
RGDEMO001  KBDemo020
```

## Apply a label to properties

You can assign friendly names to the properties that you select from the query command. The following example shows how to assign friendly names "VMName" and "RGName" to the selected properties "name" and "resourceGroup".

```azurecli
az vm list \
  --query "[].{RGName:resourceGroup, VMName:name}"
```

```json
RGName     Name
---------  -----------
DEMORG1    DemoVM010
DEMORG1    demovm111
DEMORG1    demovm211
DEMORG1    demovm212
DEMORG1    demovm213
DEMORG1    demovm214
DEMORG1    demovm222
RGDEMO001  KBDemo001VM
RGDEMO001  KBDemo020
```

## Selecting complex embedded properties

if the property you want to select is embedded deep in the JSON out, then you have to supply the full path to that embedded property. The following example shows how to select the VMName and the OS type from the vm list command.

```azurecli
az vm list \
  --query "[].{VMName:name,OSType:storageProfile.osDisk.osType}"
```

```json
VMName       OSType
-----------  --------
DemoVM010    Linux
demovm111    Linux
demovm211    Linux
demovm212    Linux
demovm213    Linux
demovm214    Linux
demovm222    Linux
KBDemo001VM  Linux
KBDemo020    Linux
```

## Filter with the contains function

Use the JMESPath `contains` function to select objects.
In this case, select the VMs in a specific resource group.

```azurecli
az vm list \
  --query "[?contains(resourceGroup,'RGD')].{ resource: resourceGroup, name: name }"
```

```json
Resource    Name
----------  -----------
RGDEMO001   KBDemo001VM
RGDEMO001   KBDemo020
```

In this case, select the VMs that have the vmSize 'Standard_DS1'.

```azurecli
az vm list \
  --query "[?contains(hardwareProfile.vmSize, 'Standard_DS1')]"
```

```json
ResourceGroup    Name       VmId                                  Location    ProvisioningState
---------------  ---------  ------------------------------------  ----------  -------------------
DEMORG1          DemoVM010  cbd56d9b-9340-44bc-a722-25f15b578444  westus      Succeeded
DEMORG1          demovm111  c1c024eb-3837-4075-9117-bfbc212fa7da  westus      Succeeded
DEMORG1          demovm211  95eda642-417f-4036-9475-67246ac0f0d0  westus      Succeeded
DEMORG1          demovm212  4bdac85d-c2f7-410f-9907-ca7921d930b4  westus      Succeeded
DEMORG1          demovm213  2131c664-221a-4b7f-9653-f6d542fbfa34  westus      Succeeded
DEMORG1          demovm214  48f419af-d27a-4df0-87f3-9481007c2e5a  westus      Succeeded
DEMORG1          demovm222  e0f59516-1d69-4d54-b8a2-f6c4a5d031de  westus      Succeeded
```

## Filter with grep

Use the [`--out`](format-output-az-cli2.md) parameter to format the output as tab-separated values
and pipe that through grep.

```azurecli
az vm list \
  --query "[].{ name: name, os: storageProfile.osDisk.osType }" \
  --out tsv  \
| grep Linux
```

## Explore with jpterm

You can pipe the command output to [JMESPath-terminal](https://github.com/jmespath/jmespath.terminal)
and experiment with your JMESPath query there.

```bash
pip install jmespath-terminal
az vm list | jpterm
```

There is a good tutorial for JMESPath at [JMESPath.org/tutorial](http:/JMESPath.org/tutoriual.html).
