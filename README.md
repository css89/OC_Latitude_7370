# OC_Latitude_7370
macOS Catalina with OpenCore on Dell Latitude 7370

Use at your own risk! I can not be held responsible for any damage done.

- Dell Latitude 13 7370
- Intel m7-6y75
- Intel HD515
- 16 GB DDR3 RAM @1600 (possible to set to 1866MHz in BIOS)
- 256 GB Hynix NVMe (APFS 4K ->nvme-cli, not mandatory)
- DW1830 WiFi AC
- Sierra Wireless EM7345 4G LTE
- QHD+ Touchscreen Display
- Realtek ALC256 Audio (rebranded as ALC3246)
- 43 Wh battery
- BIOS version 1.18.5 (you should be on the same version if you plan to use my ACPI files!)
  https://dl.dell.com/FOLDER05870297M/1/Latitude_7370_1.18.5.exe (needs to be done on Windows)
- OpenCore v0.58
- MacBook9,1 as SMBIOS (you'll need to insert your own generated serials in /EFI/OC/config.plist)




Working:
- EC power management
- HD515 with full hardware acceleration
- USB-C charging
- Audio as Apple-ALC layout-id 56(0b000000)
- display brightness control
- touchpad with scrolling and two-finger-click (VoodooPS2)
- keyboard with backlight

Not working (so far):
- 4G/LTE (had it working with clover so I'm sure I'll get it working)
- Touchscreen (had it working with clover so I'm sure I'll get it working)
- function keys (use karabiner to realocate)

Not tested (so far):
- NFC, Fingerprint or Smartcard (I don't have these built-in so I can't say)
- miniHDMI port (don't have that type of cable)
- USB-C DisplayPort/Data/Thunderbolt3
- microSD cardreader

Necessary files:
- Resources for visual bootscreen (replace Resources folder in EFI\EFI/OC/ )

Necessary tools:
- MountEFI
- ProperTree

Usefull:
- karabiner (keymap)
- one-key-hidpi (scaling for FullHD displays)

BIOS setting:
...

Things that need to be done:

1. Create macOS Installer
  - create a macOS Catalina installer preferably on a real MAC
  - mount EFI
  - download and copy the EFI folder from this repository to the EFI partition on your USB drive
    (not just the content of the EFI folder!)

2. Set UEFI Variables
  - use the macOS USB installer you created and select xxx.efi
  - disable CFG Lock: setup_var 0x109 0x00   !!!verify before use!!!extracted from BIOS 1.18.5!!!
  - only needed for QHD+ displays:
    increase DVMT:    setup_var ...          !!!verify before use!!!extracted from BIOS 1.18.5!!!

3. ...

...



 Last steps:
 - Set Keyboard to desired language

Thanks to:
Dortania on GitHub for OpenCore files and awesome documentation
https://dortania.github.io/getting-started/
