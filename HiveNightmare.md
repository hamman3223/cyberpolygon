# HiveNightmare

### **Версии windows подверженные атаке:**

- Windows 10 все версии с 1809

### **Суть атаки:**

В случае если включена System protection, то тогда создаются снэпшоты, для реализации которых навешиваются критические флаги доступа на регистры SYSTEM, SECURITY и на файл SAM.

Благодаря чему можно реализовать LPE (Local Privilege Escalation), скопировав хэши, потом сделав дамп NTLM хэшей через тулу [secretsdump.py](http://secretsdump.py) и подключиться удаленно к PS уязвимой тачки через тулу [psexec.py](http://psexec.py) указав хэш , пользака и айпи адрес компьютера жертвы. 

### **Способы митигейта:**

Удалить VSS (Volume Shadow Copy Service) копии

`vssadmin delete shadows /for=%systemdrive% /Quiet`

удостовериться, что они удалены `vssadmin list shadows`

### Референсы:

- [https://www.youtube.com/watch?v=5zdIq6t3DOw](https://www.youtube.com/watch?v=5zdIq6t3DOw)[https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-36934](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-36934)
- [https://github.com/GossiTheDog/HiveNightmare](https://github.com/GossiTheDog/HiveNightmare)