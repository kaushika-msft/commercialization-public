---
author: themar
Description: 'Create bootable WinPE media'
ms.assetid: d60de9b6-6775-41e7-bc52-dfafede554df
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'WinPE: Create bootable media'
ms.author: themar
ms.date: 04/24/2018
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-oem
---

# Create bootable WinPE media

The Windows Assessment and Deployment Kit (ADK) includes the [CopyPE](copype-command-line-options.md) and [**MakeWinPEMedia**](makewinpemedia-command-line-options.md) command line utilities. When run from the Deployment and Imaging Tools Environment, **CopyPE** creates a working set of WinPE files, that **MakeWinPEMedia** can use to create bootable WinPE media. **MakeWinPEMedia** can create bootable WinPE USB drives, virtual hard disks, or ISOs that allow you to boot a VHD or burn to a DVD or CD.

**CopyPE** and **MakeWinPEMedia** are installed when you choose the **Deployment tools** and **Windows Preinstallation Environment** options when [installing the ADK](https://docs.microsoft.com/en-us/windows-hardware/get-started/adk-install).

## Step 1: Create working files

No matter what type of media you're going to create, the first thing to do is create a working set of WinPE files on your technician PC.

1. Start the **Deployment and Imaging Tools Environment** as an administrator.

2. Run **copype** to create a working copy of the Windows PE files. For more information about copype, see [Copype command line options](copype-command-line-options.md).

    ```
    copype amd64 C:\WinPE_amd64
    ```

## Step 2: Create bootable media

Now that you now have a set of working files, you can use **MakeWinPEMedia** to build bootable WinPE media.

### Create a bootable WinPE USB drive

1. Attach a USB drive to your technician PC.

2. Start the **Deployment and Imaging Tools Environment** as an administrator.

3. **Optional** 
    You can format your USB key prior to running MakeWinPEMedia. MakeWinPEMedia will format your WinPE drive as FAT32. If you want to be able to store files larger than 4GB on your WinPE USB drive, you can create a multipartition USB drive that has an additional partition formatted as NTFS. See [Create a multipartition USB drive](winpe--use-a-single-usb-key-for-winpe-and-a-wim-file---wim.md#span-idcreateamultiplepartitionusbdrivespanoption-1-create-a-multiple-partition-usb-drive) for instructions.

4. Use **MakeWinPEMedia** with the `/UFD` option to format and install Windows PE to the USB flash drive, specifying the USB key's drive letter:

    ```
    MakeWinPEMedia /UFD C:\WinPE_amd64 P:
    ```

    > [!Warning]
    > This command reformats the partition.

    See [MakeWinPEMedia command line options](makewinpemedia-command-line-options.md) for all available options.

The bootable WinPE USB drive is ready. You can use it to [boot a PC into WinPE](boot-to-uefi-mode-or-legacy-bios-mode.md).

### Create a WinPE ISO, DVD, or CD

1. Use **MakeWinPEMedia** with the `/ISO` option to create an ISO file containing the Windows PE files:

    ```
    MakeWinPEMedia /ISO C:\WinPE_amd64 C:\WinPE_amd64\WinPE_amd64.iso
    ```

2. **Optional** Burn a DVD or CD: In Windows Explorer, right-click the ISO file, and select **Burn disc image** > **Burn**, and follow the prompts.

### Create a WinPE VHD to use with Hyper-V

Even though you can create a bootable When running Windows PE in Hyper-V, consider using an ISO file format instead of a VHD, to enable quick setup of the virtual PC. 

To install Windows PE to a VHD:

1. Create a virtual hard drive (.vhdx):

    ```
    diskpart
    create vdisk file="C:\WinPE.vhdx" maximum=1000
    attach vdisk
    create partition primary
    assign letter=V
    format fs=ntfs quick
    exit
    ```
2. Prepare the drive by using **MakeWinPEMedia**:

    ```
    MakeWinPEMedia /UFD C:\WinPE_amd64 V:
    ```

3. Detach the drive:

    ```
    diskpart
    select vdisk file="C:\WinPE.vhdx"
    detach vdisk
    exit
    ```


### Troubleshooting

1.  If Windows PE doesn't appear, try the following workarounds, rebooting the PC each time:

    -   To boot a PC that supports UEFI mode: In the firmware boot menus, try manually selecting the boot files: \\EFI\\BOOT\\BOOTX64.EFI.

    -   If your PC requires storage or video drivers to boot, try adding those same drivers to the Windows PE image. For more information, see [WinPE: Mount and Customize](winpe-mount-and-customize.md).

2.  If the PC doesn't connect to network locations, see [WinPE Network Drivers: Initializing and adding drivers](winpe-network-drivers-initializing-and-adding-drivers.md).

## <span id="related_topics"></span>Related topics


[WinPE for Windows 10](winpe-intro.md)

[WinPE: Install on a Hard Drive (Flat Boot or Non-RAM)](winpe-install-on-a-hard-drive--flat-boot-or-non-ram.md)

[WinPE: Mount and Customize](winpe-mount-and-customize.md)

[WinPE: Boot in UEFI or legacy BIOS mode](winpe-boot-in-uefi-or-legacy-bios-mode.md)

[Windows Setup Supported Platforms and Cross-Platform Deployments](windows-setup-supported-platforms-and-cross-platform-deployments.md)

 

 






