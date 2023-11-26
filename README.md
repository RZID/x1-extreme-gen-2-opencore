Thinkpad X1 Extreme Gen 2 Opencore
--

#### Opencore 0.9.6

This is the contents of the OC folder in the EFI Opencore folder structure.


### Change Airportitlwm to Ventura. (Now using Sonoma)
### Change Config.plist in the PlatformInfo section and generate your own GenSMBIOS (MacBookPro16,1)

`NOTE: Please use this as a reference for Hackintosh. You won't immediately use this without studying the system and installation tips from the start.`

`LICENSE NOTE: Use this as study material and personal use. Do not use commercially. I am not responsible for any losses related to copyright and use of this tool.`

Look and match your system first with the system I have. 
<!-- Then jump to [this section](#getting-started) -->

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
<!-- 
### Getting Started
1. [Download Opencore version 0.9.6](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.9.6) (It is recommended to use the debug version first. This repository uses the release version) and then extract.
2. Prepare the removable device and format its contents. **Hereafter it will be called FD in this section**
3. Create an EFI folder on the FD -->