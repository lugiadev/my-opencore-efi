# OpenCore EFI for Hackintosh (MacOS Sequoia 15.1)

This is a prebuilt OpenCore EFI folder tailored for running macOS Sequoia 15.1 on the following hardware configuration:

## Hardware Compatibility
- **CPU**: Intel Core i5-12400F  
- **GPU**: AMD RX 6700XT  
- **Wi-Fi Adapter**: Intel
  - **Note**: Patched for native support of Wi-Fi without Heliport.  

## Features
- Native Wi-Fi and Bluetooth functionality with Intel adapter patched as Broadcom.  
- Support for native Apple services, including iMessage and AirDrop.  
- Optimized power management and thermal controls.  
- Proper GPU acceleration for RX 6700XT.  

## Included Kexts
The following kexts are pre-configured and included in the EFI folder:  

- **Core Patches**:  
  - `AMFIPass.kext`  
  - `Lilu.kext`  
  - `RestrictEvents.kext`  

- **Wi-Fi & Bluetooth**:  
  - `AirportItlwm-2.kext`  
  - `AirportItlwm.kext`
  - `BrcmFirmwareData.kext`  
  - `BrcmPatchRAM3.kext`  
  - `IntelBTPatcher.kext`  
  - `IntelBluetoothFirmware.kext`  
  - `IO80211FamilyLegacy.kext`  
  - `IOSkywalkFamily.kext`  
  - `BlueToolFixup.kext`  

- **Audio & Graphics**:  
  - `AppleALC.kext`  
  - `AppleIGC.kext`  
  - `NootRX.kext`

- **Storage Support**:  
  - `NVMeFix.kext`  

- **Virtualization & SMBIOS**:  
  - `VirtualSMC.kext`  
  - `SMCProcessor.kext`  
  - `SMCSuperIO.kext`  

- **USB Support**:  
  - `USBMapDummy.kext`  
  - `USBToolBox.kext`  
  - `UTBMap.kext`  
  - `XHCI-unsupported.kext`  

- **Miscellaneous**:  
  - `CpuTscSync.kext`  

## Installation Steps
1. **BIOS Configuration**:  
   - Enable `VT-d`, but make sure to disable the `CFG-Lock` if available.  
   - Disable `Secure Boot`.  
   - Set boot mode to `UEFI`.  

2. **Create macOS Installer**:  
   Follow the official OpenCore guide to create a bootable USB installer for macOS.  

3. **EFI Setup**:  
   - Replace the EFI folder on the USB installer with the provided EFI folder.  

4. **Boot macOS Installer**:  
   - Boot into the OpenCore boot picker and select the macOS installer.  

5. **Post-Installation**:  
   - Generate a proper SMBIOS using the OpenCore Configurator or GenSMBIOS tool.  
   - Use OpenCore Legacy Patcher (OCLP) to finalize Wi-Fi and Bluetooth patches for native compatibility.  

## Notes
- This EFI is designed for **macOS Sequoia 15.1** and may not work for other macOS versions without modifications.  
- Ensure your hardware matches the listed configuration for the best results.  

## Troubleshooting
- If Wi-Fi or Bluetooth is not functional, ensure OCLP has patched the Intel adapter correctly.  
- For GPU issues, verify that the AMD RX 6700XT is properly connected and supported by macOS.  

## Credits
This project is made possible thanks to the contributions of the Hackintosh community, including the developers of OpenCore and the kexts listed above.  