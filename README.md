Thinkpad X1 Extreme Gen 2 Opencore
--

Opencore 0.9.6

++ Install with Ventura then update to Sonoma via OTA (Update in settings)

This is the contents of the OC folder in the EFI Opencore folder structure.

> NOTE: Please use this as a reference for Hackintosh. You won't immediately use this without studying the system and installation tips from the start.

> LICENSE NOTE: Use this as study material and personal use. Do not use commercially. I am not responsible for any losses related to copyright and use of this tool.

Look and match your system first with the system I have. Then jump to [this section](#getting-started)

### Important to note!
- Please read and follow the [installation page](https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html#prerequisites) first before starting.
- **Never reset NVRAM** on a ThinkPad device, especially this device. My device once had a problem and I finally made a warranty claim at the shop. [Here's an article related to this.](https://github.com/acidanthera/bugtracker/issues/995)

### My Specs
- Thinkpad X1 Extreme Gen 2 (20QW)
- CPU : Intel Core i7-9850H
- GPU 1 : Intel(R) UHD Graphics 630 (iGPU)
- GPU 2 : NVIDIA GeForce GTX 1650 (4 GB) (dGPU) <b>(DISABLED)</b>
- STORAGE 1 : VR M.2 NGFF 256GB  (NGFF SATA) *(Obtained from the previous owner)*
- STORAGE 2 : ADATA LEGEND 850 LITE  (PCI-E 4.0 x4) (NVME Gen 4) *(I think it will run with PCIe 3.0 instead of 4.0)*
- RAM 1 : (DIMM1: SK hynix HMA82GS6JJR8N-VK	16 GB DDR4-2666 DDR4 SDRAM)
- RAM 2 : (DIMM3: Essencore KD4AGSA80-26N190A 16 GB DDR4-2666 DDR4 SDRAM)
- DISPLAY : (Internal)	Samsung ATNA56WR08-0  [15.6" OLED] (3840 x 2160) (Touchscreen)
- WIRELESS CARD : Intel(R) Wi-Fi 6 AX200 160MHz
- WIRED NETWORK : Intel(R) Ethernet Connection (7) I219-LM
- TOUCHPAD : Synaptics
- TOUCHSCREEN : Wacom (Built-in display)
- Fingerprint (Not working)

### Getting Started
1. [Download Opencore version 0.9.6](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.9.6) (It is recommended to use the debug version first. This repository uses the release version) and then extract.
2. Prepare the removable device and format its contents. **Hereafter it will be called FD in this section**.
3. Copy the extracted Opencore Files inside X64 directory (Start copying in EFI not the X64) to FD. The result should be `FD/EFI`
4. Remove *unused* files in `FD/EFI/OC/Drivers` and `FD/EFI/OC/Tools`.
5. Clone/download this repository and extract.
6. Navigate to `FD/EFI/OC` and copy files that are not in your FD but are in this repository such as `ACPI`, `Drivers`, `Kexts` folders and `Config.plist` file.
7. Navigate back to extracted Opencore directory then navigate to `Utilities/macrecovery`.
8. Navigate to [this page](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) and select your current OS (e.g. Windows) then select what version of Mac you want to install (pay attention to the support list too). After that, follow the directions on the page to download.
9. After the download is complete, in the `Utilities/macrecovery` directory a folder called `com.apple.recovery.boot` will be created automatically. Copy the folder and paste it into `FD/`. The result will be two folders, namely `FD/EFI` and `FD/com.apple.recovery.boot`.
10. Download and open [ProperTree](https://github.com/corpnewt/ProperTree), then open the `FD\EFI\OC\Config.plist` file in ProperTree.
11. Perform an **OC Clean Snapshot** to clean up unnecessary rules.
12. Make sure in the `Root/Kernel/Add` section, the first sequence is `Lilu.kext` and the second sequence is `VirtualSMC.kext`. If not, just pull it up.
13. Download and run [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS).
14. Type `3` then enter to Generate SMBIOS, then type `MacBookPro16,1` then enter.
15. In ProperTree, navigate to `Root/PlatformInfo/Generic`. Follow the instructions there.
16. Try to boot.


### Additional Notes
- This example uses the Ventura version. I have also tried updating to Sonoma. The steps that need to be taken to upgrade to Sonoma only need to change the [AirportItlwm](https://github.com/OpenIntelWireless/itlwm/releases) version to the Sonoma version.
- If there is a stuck in the boot process, please do debug mode and find out based on the last log.
- I still haven't been able to solve the sleep issue.