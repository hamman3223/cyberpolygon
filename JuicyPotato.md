# Juicy Potato

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