# Hackintosh MSI Z370 Gaming m5
This is repository contains a working EFI for MacOS Sonoma on the MSI [z370 Gaming m5](https://www.msi.com/Motherboard/Z370-GAMING-M5/Specification).

System Specs:
- CPU: i5 8600k
- Using iGPU
- Cooler: Corsair H100i
- 16gb (2x8) Corsair Vengeance Pro 3000MHz
- M.2 TeamGroup SSD (MacOS Sonoma)
- M.2 Samsung 970 SSD (Ubuntu)
- No bluetooth/WiFi card (using ethernet)

OpenCore Specs:
- Version 1.0.1
- Referencing [Dortania's OpenCore guide](https://dortania.github.io/OpenCore-Install-Guide/)
- Used [FrostMiku's EFI](https://github.com/FrostMiKu/msi-z370-hackintosh) as a base
- Uses OpenCanopy GUI for a Linux/MacOS dual-boot

Notes:
- This EFI is currently using the *OpenHFSPlus* driver. Check Dortania's [Gathering Files](https://dortania.github.io/OpenCore-Install-Guide/ktext.html#universal) section if you want to change this.
- These SSDTs may not work for you (you can just use *ACPI - Default*), and you may need to create your own *USBMap.kext*.
- Fill in the *SystemInfo > General* section of config.plist
- I am using the integrated GPU in this system. If you want to use dedicated GPU, you must carefully go over the following sections:
  - *DeviceProperties > Add > PciRoot(0x0)/Pci(0x2,0x0)* 
  - *NVRAM > Add > 7C436110-AB2A-4BBB-A880-FE41995C9F82 > boot-args*
- Adhere to the [recommended BIOS Settings](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#intel-bios-settings)
- Follow Dortania's guide with a grain of salt. They are incredibly helpful, but some directions may not work for your board specifically.
