# Matebook 14 2020 OpenCore Hackintosh
  
The project is based on [ske1996](https://github.com/ske1996/matebook-13and14-OpenCore-Hackintosh) work ([matebook.14.2020.20210508.7z](https://github.com/ske1996/matebook-13and14-OpenCore-Hackintosh/releases/tag/20210811#:~:text=matebook.14.2020.20210508.7z))

Since the target system is my own computer, I have removed components and functions that were not present in my configuration or that I did not utilize.

# MacOS Support

- **Big Sur**
- **Monterey**
- **Ventura <sup>[from 0.9.3]</sup>**


# My configuration

- **MODEL** : Huawei Matebook 14 2020
- **CPU** : Intel i5-10210U
- **RAM** : 8GB
- **SSD** : WDC PC SN730 SDBPNTY-512G


# Changelog

<details open>
  <summary><b>Opencore 0.9.4</b></summary>
  
  ### List of changes
  
  - Upgrade Opencore 0.9.3 to 0.9.4
  - Upgrade all kexts to the latest stable version

</details>

<details>
  <summary><b>Opencore 0.9.3</b></summary>
  
  ### List of changes
  
  - Upgrade Opencore 0.9.2 to 0.9.3
  - Upgrade all kexts to the latest stable version
  - Change '-igfxblr' to '**-igfxblt**' in boot arguments (more information available [here](https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.IntelHD.en.md#fix-the-3-minute-black-screen-issue-on-cfl-platforms-running-macos-134-or-later))
  
  **MacOS Ventura is now officially supported due to a new stable wifi driver.**
  
</details>

<details>  
  <summary><b>Opencore 0.9.2</b></summary>
    
  ### List of changes
  
  - Upgrade Opencore 0.9.1 to 0.9.2
  - Upgrade all kexts to the latest stable version

</details>

<details>  
  <summary><b>Opencore 0.9.1</b></summary>
  
  ### List of changes
  
  - Upgrade Opencore 0.9.0 to 0.9.1
  - Upgrade all kexts to the latest stable version
  - Made some changes for fixing usb-c hdmi hub not working

</details>

<details>
  <summary><b>Opencore 0.9.0</b></summary>
    
  ### List of changes
  
  - Upgrade Opencore 0.8.9 to 0.9.0
  - Upgrade all kexts to the latest stable version
  
</details>

<details>
  <summary><b>Opencore 0.8.9</b></summary>
    
  ### List of changes
  
  - Upgrade Opencore 0.8.8 to 0.8.9
  - Upgrade all kexts to the latest stable version
  
</details>

<details>
  <summary><b>Opencore 0.8.8</b></summary>
    
  ### List of changes
  
  - Upgrade Opencore 0.8.7 to 0.8.8
  - Upgrade all kexts to the latest stable version
  - Start testing MacOS Ventura support. The system works but with slower wifi, probably due to beta driver.
  
</details>

<details>
  <summary><b>Opencore 0.8.7</b></summary>
    
  ### List of changes
  
  - Upgrade Opencore 0.6.5 to 0.8.7
  - ACPI
    - Change 'SSDT-AWAC.aml' with 'SSDT-RTCAWAC.aml' generated from SSDTTime
    - Remove 'SSDT-dGPU-Off.aml' and 'SSDT-RMNE.aml' not needed in my setup
    - Change 'SSDT-EC-USBX-LAPTOP.aml' with 'SSDT-EC.aml' and 'SSDT-USBX.aml' generated from SSDTTime
    - Change 'SSDT-HPET.aml' with 'SSDT-HPET.aml' generated from SSDTTime
    - Change 'SSDT-PLUG.aml' with 'SSDT-PLUG.aml' generated from SSDTTime
    - Change 'SSDT-PNLFCFL.aml' with 'SSDT-PNLF.aml' generated from SSDTTime
    - Remove 'SSDT-UIAC.aml' because I've mapped the usb port with 'USBMap.kext'
    - Change 'SSDT-XOSI.aml' with 'SSDT-XOSI.aml' generated from SSDTTime
  - KEXT
    - Update all kexts to the latest stable version
    - Remove 'CPUFriend.kext' and 'CPUFriendDataProvider.kext'
    - Remove 'NoTouchID.kext'
    - Remove 'NullEthernet.kext'
    - Remove 'USBInjectAll.kext' and put custom 'USBMap.kext' after mapping my usb port
    - Remove 'VerbStub.kext'
  
  - config.plist
    - Using OpenCore Configurator, I opened the original config.plist, made some changes (mainly cleanup), and saved it. The tool helped me a lot in this phase because many keys have different formats from the original 0.6.5 version. Editing all manually led to having many problems, while this way everything works fine.
  
</details>

# Changes Needed

The **EFI** is ready to use, you only need to generate your [PlatformInfo](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#platforminfo).

As in [ske1996](https://github.com/ske1996/matebook-13and14-OpenCore-Hackintosh) project, I use "**MacBookPro15,2**". For more info, I suggest reading the [Opencore Guide](https://dortania.github.io/OpenCore-Install-Guide/extras/smbios-support.html).

# Installation

I suggest reading the [Opencore Guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) to make the USB installation disk.

Personally, I've always used the **Online** procedure, and the installation works great both on the internal and external disk.
