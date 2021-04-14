# WSL2setup

This script allows you to quickly get up and running with WSL2 on Windows 10 Build 2004.
This script allows allows for easy installation of various Linux distros.

## Quickstart

To quickly get up and running with WSL2, open a new PowerShell window as "Admin" and run the following one-liner:

```posh
iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/janblom/WSL2setup/master/WSL2_Install.ps1'))
```

You will have to run this one-liner twice.
* Run the script once to install Windows pre-requisites and let your computer reboot 
* Follow the instructions of step 4 on this page: https://aka.ms/wsl2kernel (download AND install)
* Once after the computer re-boots to update the WSL2 kernel and install a WSL distro (Ubuntu 20.04 recommended)

## Prerequisites

You will need to have Windows 10 Build 2004 installed before you can use WSL2. If you do not already have Build 2004 or later installed, you can use [the Windows Update Assistant](https://go.microsoft.com/fwlink/?LinkID=799445) to upgrade to the latest 2004 build.

## Testing

This script is tested and working on bare-metal as well as a Hyper-V VM with nested virtualization turned on.

Make sure that Dynamic Memory is _disabled_.
To turn on nested virtualization on Windows Server 2016+ or Windows 10 you can use the following command:
```posh
(Get-VM).Name # Get a list of VM names
Set-VMProcessor -VMName [TestVMName] -ExposeVirtualizationExtensions $true 
```

WSL2 on a KVM-based VM with nested virtualization, does not appear to work.
