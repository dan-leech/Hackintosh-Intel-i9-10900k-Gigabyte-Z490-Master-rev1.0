# Hackintosh Intel i9 10900k Gigabyte Z490 Aorus Master rev1.0

I have successfully installed MacOS Catalina 10.15.7 on my i9-10900k running on a Gigabyte Z490 Aorus Master rev1.0.

You can find my EFI folder in this repository.

**Current Bootloader: OpenCore 0.6.3 (30th Oct 2020)**
**You can replace with 0.6.2 tested as well**

# Hardware
- Intel i9-10900k
- Gigabyte Z490 Aorus Master rev1.0:
	- Audio: Realtek ALC1220-VB
	- 2.5Gbit Ethernet: Intel I225-V
  - Wifi/BT: build-in Intel Wi-Fi 6 AX201
  - Two USB-C ports
- RAM: 64GB G.Skill Trident Z 3600Mhz CL18
- GPU: MSI Radeon RX 5700 XT Gaming X
- Display: Dell S2127QS connected with HDMI

# Working
- [x] **Tested with macOS Catalina 10.15.7**
- [x] **Wifi and Bluetooth** motherboard's Intel Wi-Fi 6 AX201 (AirportItlwm.v1.0b-catalina.kext, IntelBluetoothFirmware.kext, IntelBluetoothInjector.kext, [@see](https://github.com/OpenIntelWireless/itlwm))
- [x] **Audio**: Realtek ALC1220-VB (AppleALC.kext, layout-id=7, device-id=0xA170, FakeID.kext, FakePCIID_Intel_HDMI_Audio.kext)
- [x] **USB**, all ports.
- [x] **2.5Gbit Ethernet (Intel I225-V)**
- [x] **With iMac20,2: AppleTV** 
- [x] **Sleep/Wake**
- [x] **Shutdown**
- [x] **Restart**

## need post install setup with installing apps
- [x] **Britness controll from keybord**
- [x] **Volume control from keyboard**

# Not tested yet
- [ ] SideCar, Amazon Prime Video and Netflix in Safari

# Details

I followed this guide: https://www.tonymacx86.com/threads/gigabyte-z490-vision-d-thunderbolt-3-i5-10400-amd-rx-580.298642/
It's completed and has all answers about install and post install. What I've improved it's usb mapping.

* EFI/OC folder contains different configs. You need to rename one to `config.plist`

1. For install I've used `config-iGPU-install.plist` because I had not found the solution with bios name replacement for my card.
2. `config-debug.plist` has bios name replacement for MSI 5770XT cards and it should work with install to.
3. Create the install usb yourself, for some reasons downloaded usb images that I tried didn't work.
4. When you'll be sure that macos load well you can use `config-prod.plist`

## Language

Default Keyboard Layout/Language setting was changed to EN-US in v1.5.

If you want to change this, just edit this setting in the config.plist:

```
- NVRAM
	- Add
		- 7C436110-AB2A-4BBB-A880-FE41995C9F82
			- prev-lang:kbd | String | en-US:0
```

Valid Keyboard Values see here: [AppleKeyboardLayouts.txt](https://github.com/acidanthera/OpenCorePkg/blob/master/Utilities/AppleKeyboardLayouts/AppleKeyboardLayouts.txt)

# Credits
Thanks for your support :) Your help was crucial for my build.
- https://www.tonymacx86.com/threads/gigabyte-z490-vision-d-thunderbolt-3-i5-10400-amd-rx-580.298642/ this article is the briliant one for Gigabyte z490
- https://github.com/SchmockLord/Hackintosh-Intel-i9-10900k-Gigabyte-Z490-Vision-D : This repository helps me a lot too
- https://github.com/SwimmingPig/Hackintosh-Intel-i5-10400-Gigabyte-Z490M-Gaming-X and this one
- [Dortania](https://github.com/dortania) for this great OpenCore Desktop Guide
- [headkaze](https://github.com/headkaze) for Hackintool and our productive conversations :)
- [Acidanthera](https://github.com/acidanthera) for too many things to mention each
- [RehabMan](https://github.com/RehabMan) for too many things to mention each
- [OpenCore project](https://github.com/OpenCorePkg) for this great bootloader

Best,
Chris 
aka SchmockLord
