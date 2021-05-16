# OpenCore Hackintosh Catalina For Asus ROG Strix Z390-H Gaming Motherboard
This is a vanilla setup with [OpenCore](https://github.com/acidanthera/OpenCorePkg "OpenCore") as boot loader. I have used [this guide](https://dortania.github.io/OpenCore-Install-Guide/ "OpenCore Desktop Guide") for creating and configuring the `EFI` folder, and will try to keep up to date with new OpenCore and MacOS releases for this is my daily drive.

![About This Mac](assets/about.png)

## Hardware 

| Component   | Model/Brand                         | Notes                                                                                                                                                                                  |
|-------------|-------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CPU         | Intel Core i7 9700K                 | Any required configurations is present in the `EFI`                                                                                                                                    |
| Motherboard | Asus ROG Strix Z390-H Gaming        | You need to apply [these BIOS settings](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#intel-bios-settings)                                           |
| RAM         | Kingston 16GB 2400MHZ DDR4          | Two sticks, totaling to 32 GB                                                                                                                                                          |
| GPU         | Sapphire Pulse AMD Radeon RX 5700XT | With `WhateverGreen` kext and `agdpmod=pikera` parameter. (Already configured)                                                                                                         |
| Bluetooth   | Trust 18187 Bluetooth 4.0 Adaptor   | Dongle, works out of the box                                                                                                                                                           |
| SMBIOS      | iMac19,2                            | While provided serial works, you may want to generate your own.   Refer to this [guide](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#platforminfo). |

---
**NOTE**

If you wish to have wi-fi functionality you should purchase a `Broadcom BCM94360NG` card and plug it in. No other configurations are needed.

---

## Configuration
There some changes to should make in the BIOS. For a complete list [refer here](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#intel-bios-settings). Below are the screenshots to guide you through this process.

- Disable `CGF Lock` 
  - ![cfg_lock](assets/cgf_lock.png)
- Disable `SGX` 
  - ![sgx](assets/sgx.png)
- Disable `VT-d` and enable `Above 4G decoding` 
  - ![vt_d](assets/vt_d.png)
- Set `SATA` mode to `AHCI` 
  - ![ahci](assets/ahci.png)
- Disable serial port 
  - ![serial_port](assets/serial_port.png)
- Enable `XHCI Hand Off` 
  - ![hand_off](assets/xhci_hand_off.png)
- Disable fast boot 
  - ![fast_boot](assets/fast_boot.png)
- Disable `CSM` 
  - ![csm](assets/csm.png)
- Set OS type 
  - ![os_type](assets/os_type.png)

## Installing
Download the `EFI` folder from [releases](https://github.com/hamido/opencore-efi-asus-z390-h/releases) and unzip it under the EFI partition. Provided that the hardware is identical and configurations are the same it should "just" work :crossed_fingers:

## What works

- :white_check_mark: Sleep/Wake
- :white_check_mark: Ethernet
- :white_check_mark: Bluetooth
- :white_check_mark: USB ports
- :white_check_mark: Audio
- :white_check_mark: CPU power management
- :white_check_mark: USB mapping
- :white_check_mark: ACPI