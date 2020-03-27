# All topics related to windows (beta version)

## First check BIOS type, then make bootable device, finally follow Win10 installation procedures; if any issues troubleshoot it via supported link or do some googlingl;

[For more about BIOS firmware type (Windows installation)](https://neosmart.net/wiki/windows-wont-start/)
### To Check if Windows 10 is using UEFI or Legacy BIO (A-way)
1.  ``` bcdedit | find "path ``` (recommended) or ``` bcdedit ``` : *if* **\Windows\system32\winload.exe** = Legacy BIOS; *if* **\Windows\system32\winload.efi** = UEFI
### To Check if Windows 10 is using UEFI or Legacy BIO (B-way)
2. ``` wpeutil UpdateBootInfo ``` will get *will get a message that command completed successfully*
2.1 ``` reg query HKLM\System\CurrentControlSet\Control /v PEFirmwareType ``` : *if* the PEFirmwareType DWORD shows as **0x1** = (legacy BIOS); *if* **0x2** = (UEFI)

---
## All about Win10 installation process:
[Link on how to create a bootable usb flash for windows installation process](https://www.tenforums.com/tutorials/2376-create-bootable-usb-flash-drive-install-windows-10-a.html)
### Partition scheme on Rufus (*depending on which type of BIOS your motherboard is compatible with*):
a) MBR meant for BIOS LEGACY
b) GPT meant for UEFI (newest), *unless you have UEFI-CMS that would accept MBR*
### Format file system: 
a) FAT32 up to 2 GB; use the software recommend cluster size!
b) NTFS for more than 2 GB (newest) ***use this is one is a good practice***; use the software recommend cluster size! It's (4096 bytes)
[For more read this](https://www.howtogeek.com/136078/what-should-i-set-the-allocation-unit-size-to-when-formatting/)

### Format file system: during Win10 installtion the installation process itself may require to convert (steps below):
```diff
- Caution! Selected disk conversion will wipe out all files within that particular disk!
```
Firstly press  ``` Shift + F10  ``` so to open a command prompt, then do the following commands:

1. ```list disk```
2. ```select disk <No.>``` *where as <No.> is specific disk number*
3. ```clean```
4. ```convert gpt```
5. ```exit```

**Bonus commands:**
- Type ```shutdown /s```  to Shutdown your windows PC; *usually does not work via windows installation process*
- Type ```shutdown /r ``` to Restart your windows PC; *usually does not work via windows installation process*

---

[Link on how to install clean Win10](https://www.tenforums.com/tutorials/1950-clean-install-windows-10-a.html)
**During installation of Win10 we might need SATA drivers** [Link on how to upload SATA drivers to usb flash drive](https://www.eightforums.com/threads/sata-driver-load-in-windows-8-setup.9573/)

---

## Debugging mode for Windows "not booting" issues:

[For more read this](https://neosmart.net/wiki/windows-wont-start/)
### Enable safe mode via CMD
``` bcdedit /set {default} safeboot minimal ``` 
### Disable safe mode via CMD
``` bcdedit /deletevalue {current} safeboot ```
