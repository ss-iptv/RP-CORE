# <div align="center">RP CORE — Universo Hackintosh</div>

<div align="center"><img width="1562" height="895" alt="RP-CORE-1 0 1" src="https://github.com/user-attachments/assets/eb6ebd33-e86a-48fc-bdd5-c49209a27195" /></div>

Script to apply **Root Patching** (SSV snapshot) for:

- **WiFi (BCM94360/Intel)** on macOS **Sonoma (14)**, **Sequoia (15)** and **Tahoe (26)**
- **Audio (AppleHDA)** **only** on macOS **Tahoe (26)** 

---

## Key features

- **Automatic detection** of the macOS version to apply the correct patch.
- **Compatible with** WiFi (Fenvi/BCM94360 and Intel) and Audio (any codecs).
- **Log generation** in the script's ./logs directory, saved automatically.
- **100% transparent** in Shell Script + Python.
- **EFI validation** from config.plist for mandatory requirements to apply this patch.
- **Modular System** for applying patches (WiFi Only, Audio Only or WiFi + Audio).
- **Snapshots Management** for modular patches.
- **Without any Login Items** in your Setup for audio/wifi work.

---

## Important requirements

- **SIP Partially Disabled**
    - `csr-active-config` = `03080000`;
- **FileVault Off/Disabled**
    - `fdesetup status`;    
- **Kexts loaded in your EFI**
    - For BCM94360 (AMFIPass.kext, IO80211FamilyLegacy.kext, IOSkywalkFamily.kext and AirPortBrcmNIC.kext)
    - For Intel (AirportItlwm.kext/Ventura)
    - For Audio (AppleALC.kext)
- **Kernel/Block Patches**
    - `Allow IOSkywalk Downgrade - Patch for activate BCM Wireless`
- **Permission to load AMFIPass Beta**
    - `-amfipassbeta` on `boot-args`
- **Gatekeeper disabled**, or execution manually allowed in System Settings > Privacy & Security;
    - `sudo spctl --master-disable`
- **Audio Activation** requires KDK that matches with your macOS
    - Without correct KDK = error or stuck boot OR;
    - Error applying the patch.
- **Hackintosh technical knowledge**
    - At least at a basic/intermediate level for troubleshooting if problems occur.

---

## Credits

- [Apple](https://www.apple.com)
    - macOS
- [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher)
    - Root Patches
- [EduCovas](https://github.com/covasedu)
    - WiFi Drivers/Patches
