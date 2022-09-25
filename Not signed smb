SMB relay
=========

Кто подвержен данной атаке
--------------------------

Microsoft ещё в 2008 выпустила бюллетень безопасности [MS08-068](https://technet.microsoft.com/library/security/ms08-068 "MS08-068") и соответствующий патч для Windows, но если на узле не реализована подпись пакетов "SMB Signing", тогда атака может быть успешно реализована.

Как происходит атака
--------------------

По сути это атака типа "человек по середине". "Атакующий" каким-либо образом вмешивается в процесс подключения пользователя к серверу, после перехватывает все данные, которые передает клиент серверу и наоборот, а после авторизуется на сервере вместо клиента. Клиенту же приходит отправляется сообщается, что он ошибся при вводе данных.

Полезные ссылки
---------------

CrackMapExec: [command reference](https://github.com/Porchetta-Industries/CrackMapExec/wiki/SMB-Command-Reference)
Nmap: [nmap cheat sheet](https://www.stationx.net/nmap-cheat-sheet/)
Metasploit: [smb relay](https://subscription.packtpub.com/book/security/9781788623179/11/ch11lvl1sec132/smb-relay-attacks)
