[For more read this](https://neosmart.net/wiki/windows-wont-start/)
### Enable safe mode via CMD
``` bcdedit /set {default} safeboot minimal ``` 
### Disable safe mode via CMD
``` bcdedit /deletevalue {current} safeboot ```

---

[For more about BIOS firmware type (Windows installation)](https://neosmart.net/wiki/windows-wont-start/)
### To Check if Windows 10 is using UEFI or Legacy BIO (A-way)
1.  ``` bcdedit | find "path ``` (recommended) or ``` bcdedit ``` : *if* **\Windows\system32\winload.exe** = Legacy BIOS; *if* **\Windows\system32\winload.efi** = UEFI
### To Check if Windows 10 is using UEFI or Legacy BIO (B-way)
2. ``` wpeutil UpdateBootInfo ``` will get *will get a message that command completed successfully*
2.1 ``` reg query HKLM\System\CurrentControlSet\Control /v PEFirmwareType ``` : *if* the PEFirmwareType DWORD shows as **0x1** = (legacy BIOS); *if* **0x2** = (UEFI)
