---
uid: Installation1-0
---

# Install EdgeCmd utility

The following sections provide instructions for installing the EdgeCmd utility on Windows or Linux.

## Windows

**Note:** You must have administrative privileges to install the software. 

Complete the following steps to install the EdgeCmd utility on Windows:

1. Copy the _EdgeCmd.msi_ file to the file system of the device.
2. To start the installer, double-click the _EdgeCmd.msi_ file in Windows Explorer.

   **Note:** To change the install path from the default path of C:\Program Files\OSIsoft\EdgeCmd, enter the following command in the command prompt and update the <file_path>. OSIsoft recommends you use the default path.
    
    ```bash
    msiexec /i EdgeCmd.msi INSTALLFOLDER=<file_path>
    ```

   **Note:** INSTALLFOLDER must be in all caps.

The EdgeCmd utility is installed on the device.

## Linux

**Note:** You must have administrative privileges to install the software, for example, root or sudo privilege. 

Complete the following steps to install the EdgeCmd utility on Linux:

1. Open a terminal window and type the sudo command for the appropriate EdgeCmd deb file for your processor:

    **Debian 9 or later (Intel/AMD 64-bit processors)**

    ```bash
    sudo apt install ./EdgeCmd_linux-x64.deb
    ```

    **Debian 9 or later (ARM32, Raspberry PI 2,3,4: Raspbian, BeagleBone)**

    ```bash
    sudo apt install ./EdgeCmd_linux-arm.deb
    ```

    ![alt text](https://osisoft.github.io/Edge-Data-Store-Docs/V1/images/LinuxInstall1.jpg "Linux Installation")

    **Debian 9 or later (Raspberry PI 3,4: Ubuntu ARM64 Server, Google Coral Dev Board, Nvidia Nano Jetson)**

    ```bash
    sudo apt install ./EdgeCmd_linux-arm64.deb
    ```

    A validation check for prerequisites will be completed. If the Linux OS is up to date, the install will complete and the EdgeCmd utility will be available on your device.

2. If the install fails, run the following commands from the terminal window and try the install again:

    ```bash
    sudo apt update
    sudo apt upgrade
    ```
