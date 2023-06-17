# Matebook 14 2020 OpenCore Hackintosh
  
The project is based on [ske1996](https://github.com/ske1996/matebook-13and14-OpenCore-Hackintosh) work ([matebook.14.2020.20210508.7z](https://github.com/ske1996/matebook-13and14-OpenCore-Hackintosh/releases/tag/20210811#:~:text=matebook.14.2020.20210508.7z))

Since the target system is my computer I've removed something that my configuration didn't have or function I didn't use.

# MacOS Support

- **Big Sur**
- **Monterey**
- **Ventura <sup>[from 0.9.3]</sup>**


# My configuration

- **MODEL** :	Huawei Matebook 14 2020
- **CPU** :	Intel i5-10210U
- **RAM** :	8GB
- **SSD** :	WDC PC SN730 SDBPNTY-512G


# Changelog

<details open>
  <summary><b>Opencore 0.9.3</b></summary>
  
### List of changes
  
  - Upgrade Opencore 0.9.2 to 0.9.3
  - Upgrade all kext to last stable version
  - Change '-igfxblr' to '**-igfxblt**' in boot argument (more info <a href="https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.IntelHD.en.md#fix-the-3-minute-black-screen-issue-on-cfl-platforms-running-macos-134-or-later">here</a>)
  
  **MacOS Ventura is now officially supported due to new stable wifi driver.**
  
</details>

<details>  
  <summary><b>Opencore 0.9.2</b></summary>
    
### List of changes
  
  - Upgrade Opencore 0.9.1 to 0.9.2
  - Upgrade all kext to last stable version

</details>

<details>  
  <summary><b>Opencore 0.9.1</b></summary>
  
### List of changes
  
- Upgrade Opencore 0.9.0 to 0.9.1
- Upgrade all kext to last stable version
- Made some change for fixing usb-c hdmi hub not working

</details>

<details>
  <summary><b>Opencore 0.9.0</b></summary>
    
### List of changes
  
  - Upgrade Opencore 0.8.9 to 0.9.0
  - Upgrade all kext to last stable version
  
</details>

<details>
  <summary><b>Opencore 0.8.9</b></summary>
    
### List of changes
  
  - Upgrade Opencore 0.8.8 to 0.8.9
  - Upgrade all kext to last stable version
  
</details>

<details>
  <summary><b>Opencore 0.8.8</b></summary>
    
### List of changes
  
  - Upgrade Opencore 0.8.7 to 0.8.8
  - Upgrade all kext to last stable version
  - Start testing MacOS Ventura support. The system works but with slower wifi probably due to beta driver.
  
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
    - Remove 'SSDT-UIAC.aml' because i've mapped the usb port with 'USBMap.kext'
    - Change 'SSDT-XOSI.aml' with 'SSDT-XOSI.aml' generated from SSDTTime
  - KEXT
    - Update all kext to last stable version
    - Remove 'CPUFriend.kext' and 'CPUFriendDataProvider.kext'
    - Remove 'NoTouchID.kext'
    - Remove 'NullEthernet.kext'
    - Remove 'USBInjectAll.kext' and put custom 'USBMap.kext' after mapping my usb port
    - Remove 'VerbStub.kext'
  
  - config.plist
    - Using OpenCore Configurator I've opened the original config.plist, make some change (mainly cleanup) and saved. The tool help me a lot in this phase because many keys have different format from the original 0.6.5 version. Editing all manualy lead to have a lot of problem while in this way all work fine.
  
</details>

# Change Needed

The **EFI** is ready to use, you only have to generate your [PlatformInfo](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#platforminfo).

Like in [ske1996](https://github.com/ske1996/matebook-13and14-OpenCore-Hackintosh) project I use "**MacBookPro15,2**" but for more info I suggest to read [Opencore Guide](https://dortania.github.io/OpenCore-Install-Guide/extras/smbios-support.html).

# Installation

I suggest read [Opencore Guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) for making the USB install disk.

Personally I've always used the **Online** procedure and the installation works great both on internal and external disk.
