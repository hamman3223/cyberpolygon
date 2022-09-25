# JuicyPotato/PrintSpoofer/RoguePotat

# JuicyPotato

### **Версии windows подверженные атаке:**

- Windows_10_Enterprise
- Windows_10_Pro
- Windows_7_Enterprise
- Windows_8.1_Enterprise
- Windows_Server_2008_R2_Enterprise
- Windows_Server_2012_Datacenter

### **Суть атаки:**

Уязка заключается в том, что сервис учеткам (COM учеткам) выдаются флаги привилегий  **SeImpornatePrivilege** или **SeAssignPrimaryTokenPrivilege**

Такие COM учетки есть у таких сервисов как IIS или SQL сервисы.

### Условия реализации атаки:

1. Юзер аккаунт имеет привилегии **SeImpersonatePrivilege** или **SeAssignPrimaryTokenPrivilege**
2. COM сервер с уникальным CLSID (Class ID - уникальный идентификатор приложухи/сервиса в винде)
3. Порт для прослушивания, который мы запускать из под COM сервера
4. Адрес атакующего
5. Netcat или готовый реверс шел из msfvenom’а

<aside>
💡 COM сервер обычно представляет из себя исполняемый файл (EXE или DLL) который реализует ряд COM объектов. (COM объекты работает как API-ка определенных методов, предназначенных для коммуникации с компонентами Windows (Windows shell, ActiveX, COM+ и другая шелуха)

COM сервера имеют записи в регистре, а также CLSID и APPID

</aside>

### Референсы:

- **HTB (тачки Bounty, Jeeves и Conceal)**
- [https://medium.com/r3d-buck3t/impersonating-privileges-with-juicy-potato-e5896b20d505](https://medium.com/r3d-buck3t/impersonating-privileges-with-juicy-potato-e5896b20d505)

# PrintSpoofer

### **Версии windows подверженные атаке:**

1. Windows 10
2. Server 2016/2019

### Суть атаки:

Уязка также эксплойтит **SeImpersonatePrivelege** и вдобавок **SeAssignPrimaryTokenPrivilege**.

### Условия реализации:

По сути такие же как и у JuicyPotato

### Референсы:

- Описание эксплойта ([https://itm4n.github.io/printspoofer-abusing-impersonate-privileges/](https://itm4n.github.io/printspoofer-abusing-impersonate-privileges/))
- Краткое описание ([https://github.com/itm4n/PrintSpoofer/blob/master/demo.gif](https://github.com/itm4n/PrintSpoofer/blob/master/demo.gif))

# RoguePotato

### Версии windows подверженные атаке:

- Windows 10 1809 +

### Суть атаки

Уязка эксплойтит флаг permisions’ов **SeAssignPrimaryTokenPrivilege**

### **Условия реализации:**

Тяжелый случай, реализуется через RPC Server… Нужно вдаваться в глубокие подробности, чтобы понять эксплойт. Думаю такого комплексного случая не будет на киберполигоне

### Референсы:

- В ходе решения лабы встречается кейс RoguePotato ([https://0xdf.gitlab.io/2021/04/10/htb-apt.html](https://0xdf.gitlab.io/2021/04/10/htb-apt.html))