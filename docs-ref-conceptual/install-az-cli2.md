---
title: Install the Azure CLI 2.0 (Preview) | Microsoft Docs
description: Reference docs for Azure CLI 2.0
keywords: Azure CLI 2.0 (Preview), Azure CLI 2.0 Reference, Install Azure CLI 2.0, Azure Python CLI
author: allclark
manager: douge
ms.author: allclark
ms.date: 11/15/2016
ms.topic: reference
ms.prod: azure
ms.technology: azure
ms.devlang: azure-cli
ms.assetid: ea5c0ee1-c530-4a1e-a83f-e1be71f6d416
---

# Install Azure CLI 2.0 (Preview)

## OS X
```
curl -L https://aka.ms/InstallAzureCli | bash
```

## Ubuntu

### Ubuntu 12.04 LTS
On a fresh Ubuntu 12.04 VM, install the CLI by executing the following.
Python 2.7.3 should be already on the machine.

```shell
sudo apt-get update && sudo apt-get install -y libssl-dev libffi-dev python-dev
curl -L https://aka.ms/InstallAzureCli | bash
```

#### Known warnings
Warning 1:
You may see the following warning message during install and execution of `az`.
```shell
/usr/local/az/envs/default/local/lib/python2.7/site-packages/pip/pep425tags.py:30: RuntimeWarning: invalid Python installation: unable to open /usr/az/envs/default/lib/python2.7/config/Makefile (No such file or directory)
  warnings.warn("{0}".format(e), RuntimeWarning)
```
See also https://github.com/pypa/pip/issues/1074.

### Ubuntu 14.04 LTS and BASH on Windows (Build 14362+)
Python 2.7.6 should be already on the machine.

```shell
sudo apt-get update && sudo apt-get install -y libssl-dev libffi-dev python-dev
curl -L https://aka.ms/InstallAzureCli | bash
```

### Ubuntu 15.10
Python 2.7.10 should be already on the machine.
```shell
sudo apt-get update && sudo apt-get install -y libssl-dev libffi-dev python-dev build-essential
curl -L https://aka.ms/InstallAzureCli | bash
```

### Ubuntu 16.04 LTS
Python 2.7.11 should be already on the machine.
```shell
sudo apt-get update && sudo apt-get install -y libssl-dev libffi-dev python-dev build-essential
curl -L https://aka.ms/InstallAzureCli | bash
```

## Debian

### Debian 7
Python 2.7.3 should be already on the machine.
```shell
sudo apt-get update && sudo apt-get install -y libssl-dev libffi-dev python-dev
curl -L https://aka.ms/InstallAzureCli | bash
```

### Debian 8
Python 2.7.9 should be already on the machine.
```shell
sudo apt-get update && sudo apt-get install -y libssl-dev libffi-dev python-dev build-essential
curl -L https://aka.ms/InstallAzureCli | bash
```

## CentOS

### CentOS 6.5 / 6.6 / 6.7

Not supported with the default version of Python (2.6.6) on the machine.  We recommend using [Docker](#docker) to access the CLI on this platform.

### CentOS 7.1 / 7.2
Python 2.7.5 should be already on the machine.
```shell
sudo yum check-update; sudo yum install -y gcc libffi-devel python-devel openssl-devel
curl -L https://aka.ms/InstallAzureCli | bash
```

## RedHat RHEL

### RedHat RHEL 6.7

Not supported with the default version of Python (2.6.6) on the machine.  We recommend using [Docker](#docker) to access the CLI on this platform.

### RedHat RHEL 7.2
Python 2.7.5 should be already on the machine.
```shell
sudo yum check-update; sudo yum install -y gcc libffi-devel python-devel openssl-devel
curl -L https://aka.ms/InstallAzureCli | bash
```

## SUSE OpenSUSE 13.2
Python 2.7.8 should be already on the machine.
```shell
sudo zypper refresh && sudo zypper --non-interactive install gcc libffi-devel python-devel openssl-devel
curl -L https://aka.ms/InstallAzureCli | bash
```

## CoreOS Stable-899.15.0 / Beta-1010.1.0 / Alpha-1010.1.0

Doesn't have python installed by default and is not currently supported.  We recommend using [Docker](#docker) to access the CLI on this platform.

## Windows

The CLI is available for Windows though PIP using the steps below.  If you do not have Python/PIP installed, consider using [Docker](#docker) to access the CLI.

### Step 1: Install Python 3.5.x

If Python 2.7, 3.4 or 3.5 is already installed, skip to step 2.

Visit the Python site and [download Python 3.5](https://www.python.org/downloads/release/python-352/) for your OS.  
> **NOTE**: We recommend checking the "Add Python 3.5 to PATH" option during install.
Once the install is complete, if you open a new command prompt, you should test your Python installation:

```shell
    C:\temp> python --version
    Python 3.5.2
```

### Step 2: Install Azure CLI using PIP

Run the following from a command prompt to install the Azure CLI 2.0 using the Python package manager, PIP:

```shell
    C:\temp> pip install azure-cli
```

And after the installation complete, you can run the Azure CLI 2.0 from the command prompt:

```shell
   C:\temp> az
```

## Docker

> Note that our docker images contain the latest code from the master branch.

Run 
```shell
docker run -it azuresdk/azure-cli-python:latest bash`
```

## Installation Troubleshooting
-------------------------------

### Errors with curl redirection

If you get an error with the curl command regarding the `-L` parameter or an error saying `Object Moved`, try using the full url instead of the aka.ms url:
```shell
# If you see this:
$ curl -L https://aka.ms/InstallAzureCli | bash
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   175  100   175    0     0    562      0 --:--:-- --:--:-- --:--:--   560
bash: line 1: syntax error near unexpected token `<'
'ash: line 1: `<html><head><title>Object moved</title></head><body>

#### Try this instead:
$ curl https://azurecliprod.blob.core.windows.net/install | bash
```


### Errors on install with cffi or cryptography

If you get errors on install on **OS X**, upgrade pip by typing:

```shell
    pip install --upgrade --force-reinstall pip
```

If you get errors on install on **Debian or Ubuntu** such as the examples below,
install libssl-dev and libffi-dev by typing:

```shell
    sudo apt-get update
    sudo apt-get install -y libssl-dev libffi-dev
```

Also install Python Dev for your version of Python.

Python 2:

```shell
    sudo apt-get install -y python-dev
```

Python 3:

```shell
    sudo apt-get install -y python3-dev
```

Ubuntu 15 may require `build-essential` also:

```shell
    sudo apt-get install -y build-essential
```

### Example Errors

```shell
    Downloading cffi-1.5.2.tar.gz (388kB)
      100% |################################| 389kB 3.9MB/s
      Complete output from command python setup.py egg_info:

          No working compiler found, or bogus compiler options
          passed to the compiler from Python's distutils module.
          See the error messages above.
          (If they are about -mno-fused-madd and you are on OS/X 10.8,
          see http://stackoverflow.com/questions/22313407/ .)

      ----------------------------------------
    Command "python setup.py egg_info" failed with error code 1 in /tmp/pip-build-77i2fido/cffi/
```

```shell
    #include <openssl/e_os2.h>
                             ^
    compilation terminated.
    error: command 'x86_64-linux-gnu-gcc' failed with exit status 1

    Failed building wheel for cryptography
```

See Stack Overflow question - [Failed to install Python Cryptography package with PIP and setup.py](http://stackoverflow.com/questions/22073516/failed-to-install-python-cryptography-package-with-pip-and-setup-py)

## More Samples and Snippets
For more usage examples, take a look at our [GitHub samples repo](http://github.com/Azure/azure-cli-samples).

## Reporting issues and feedback
If you encounter any bugs with the tool please file an issue in the [Issues](https://github.com/Azure/azure-cli/issues) section of our GitHub repo.
To provide feedback from the command line, try the `az feedback` command.
