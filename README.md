
# Hackintosh-Sonoma-HP-Pavilion-15-dk00xxxx-OpenCore


**Status: (Active)** <br>
**Current version: Sonoma 14.1**

[![OpenCore](https://img.shields.io/badge/OpenCore-0.9.7-blue.svg)](https://github.com/acidanthera/OpenCorePkg)

## Introduction

**DISCLAIMER:**
Read the entire [Dortania](https://dortania.github.io/OpenCore-Install-Guide) guide before you start. I'm not responsible for any damage.

<details>
<summary>
    <strong>Hardware configuration</strong>
</summary>

### **HP Pavilion Gaming 15-**dk0047nl



 | Component       | Manufacturer and model                                | Additional description           |
 | --------------- | ----------------------------------------------------- | -------------------------------- |
 | CPU             | Intel Core i7-9750H (9th gen - Coffee Lake Plus)      |                                  |
 | GPU             | Intel Graphics UHD 630                                |                                  |
 | External GPU    | NVIDIA GeForce GTX 1650 Graphics 4 GB GDDR5           | Disabled via SSDT                |
 | Screen          | 15.6" FHD IPS anti-glare (1920 x 1080)                |                                  |
 | RAM             | 16 GB DDR4 2667 MHz                                   |                               |
 | SSD Primary     | Sabrent M.2 NVME|Disk for Windows macOS and SysLinuxOS|       
 | SSD Secondary   | SanDisk SSD PLUS 480GB SATA| SysLinuxOS and Debian    |
 | Audio           | Realtek ALC285                                        |                                  |
 | Wireless        | Intel Wireless AC 3168NGW                             |                                  |
 | LAN             | Realtek RTL8168/8111 PCI-E Gigabit Ethernet Adapter   |                                  |
 | SD card reader  | Alcor Micro AU6625 PCI-E                              | Not working
 | BIOS version    | F.63                                                  |                                  |

</details>  


<details>
<summary>
    <strong>UEFI drivers</strong>
</summary>

|     Driver      | Version           |
| :-------------: | :---------------: |
| HfsPlus.efi | OpenCorePkg 0.9.7 |
| OpenCanopy.efi  | OpenCorePkg 0.9.7 |
| OpenRuntime.efi | OpenCorePkg 0.9.7 |

</details>

<details>
<summary>
    <strong>Neofetch screenshot</strong>
</summary>

<img src="https://github.com/fconidi/Hackintosh-Sonoma-HP-Pavilion-15-dk00xxxx-OpenCore/blob/main/neofetch.png" alt="Neofetch screenshot" width="100%"/>

</details>

## Recommended UEFI/BIOS settings

<details>  
<summary>
    <strong>UEFI/BIOS Setup</strong>
</summary>

<summary>
    <strong>Security</strong>
</summary>

- `Intel Software Guard Extensions (SGX) -> Disabled`
- `TPM Device -> Disabled`

<summary>
    <strong>Configuration</strong>
</summary>

- `Virtualization Technology -> Enabled`
- `Hyper-Threading -> Enabled`

<summary>
    <strong>Boot Options</strong>
</summary>

- `Legacy Support -> Disabled`
- `Secure Boot -> Disabled`

</details>


## Configuration advices (config.plist)

You can find configuration guide for Coffee Lake Plus laptops on [dortania.github.io](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#starting-point) site.


</details>

<details>
<summary>
    <strong>PlatformInfo</strong>
</summary>

    Automatic -> True
    CustomMemory -> False
    UpdateDataHub -> True
    UpdateNVRAM -> True
    UpdateSMBIOS -> True
    UpdateSMBIOSMode -> Create
    UseRawUuidEncoding -> False

- **Generic**
  - `AdviseWindows -> False`
  - `MaxBIOSVersion -> False`
  - `ProcessorType -> 0`
  - `ROM -> 11223344 5566`
  - `SpoofVendor -> True`
  - `SystemMemoryStatus -> Auto`

 **Note**: You need to generate your own values for `SystemProductName`, `SystemSerialNumber`, `MLB` and `SystemUUID` using [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS).
 I'm using SMBIOS for MacBookPro16.4, in MacOS Ventura MacBookPro16.1.

</details>

   **Note**: For `boot-args` We need `-igfxblr` flag to prevent black screen on system loading screen.


## Status

<details>  
<summary>
    <strong>Not working ❌</strong>
</summary>
    
- `SD Card Reader`

</details>


<details>  
<summary>
    <strong>Working ✅</strong>
</summary>

- `App Store`
- `Audio` - Realtek ALC285 with sound keys (F7 and F8)
- `Brightness Keys` 
- `Battery` (management, percentage and actual work time)
- `Bluetooth and Wi-Fi` - Intel Wireless-AC 3168NGW
- `CPU power management / performance`
- `Ethernet port` - Realtek RTL8168/8111
- `Keyboard`
- `IGPU Intel UHD 630`
- `Internal microphone`
- `SATA SSD / NVMe support`
- `Shutdown / Reboot functions`
- `Sleep/Wake` 
- `Speakers and headphones combo jack`
- `System updates` 
- `Touchpad`
- `USB Ports`
- `Web camera`
- `iMessage`
- `FaceTime`
- `iTunes Store`
  
</details>



<details>  
<summary>
    <strong>rEFInd Boot Manager </strong>
</summary>

I use 4 different operating systems on my laptop (macOS, Windows 11, SysLinuxOS, Debian)
and it's necessary for me to select proper system to work on every boot.
So I decided to use rEFInd Boot Manager
</details>

## Credits

<summary>
    <strong>Thanks to:</strong>
</summary>

- [Apple](https://www.apple.com) 
- [Acidanthera](https://github.com/acidanthera) team - for OpenCore and necessary kernel extensions
- [CorpNewt](https://github.com/corpnewt) and [headkaze](https://github.com/headkaze/Hackintool) - for useful tools to install and configure system
- [Dortania](https://github.com/dortania) team - for great Hackintosh tutorials
- [OpenIntelWireless](https://github.com/OpenIntelWireless) team - for enable of laptop default Intel Wireless Wi-Fi card.
- [Mieze](https://github.com/Mieze/RTL8111_driver_for_OS_X/releases) - for enable of laptop default Realtek sound card
- [VoodooI2C](https://github.com/VoodooI2C) team - for enable of laptop keyboard
- [KrolSeb](https://github.com/KrolSeb) -  for great Hackintosh README that was my inspiration for this document
- ... and the rest of not mentioned people who works on Hackintosh project :)
