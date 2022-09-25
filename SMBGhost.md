# SMBGhost

### **Версии windows подверженные атаке:**

- Windows 10 Version 1903 for 32-bit Systems
- Windows 10 Version 1903 for ARM64-based Systems
- Windows 10 Version 1903 for x64-based Systems
- Windows 10 Version 1909 for 32-bit Systems
- Windows 10 Version 1909 for ARM64-based Systems
- Windows 10 Version 1909 for x64-based Systems
- Windows Server, version 1903 (Server Core installation)
- Windows Server, version 1909 (Server Core installation)

**Версии SMB подверженные атаке:**

- **SMB 3.1.1 (в соответствии с версиями Windows)**

### Суть атаки:

Реализет переполнение буфера на серверах Microsoft SMB. Уязка проявляется, когда сервер SMB пытается обработать вредоносный пакет сжатых данных

### Способы митигейта:

- Отключить компрессию следующим скриптов (**Set-ItemProperty -Path «HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters» DisableCompression -Type DWORD -Value 1 –Force**)
- Отключить на периметре 443-ый порт

### Референсы:

- [https://www.kaspersky.ru/blog/smb-311-vulnerability/27594/](https://www.kaspersky.ru/blog/smb-311-vulnerability/27594/)
- [https://msrc.microsoft.com/update-guide/en-US/vulnerability/CVE-2020-0796](https://msrc.microsoft.com/update-guide/en-US/vulnerability/CVE-2020-0796)