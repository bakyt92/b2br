Всем приветики в этом чатике

Хороший источник по этому проекту - у Ани
Тут будут заметки

Вообще неплохая заметка как все быстро установить 
https://www.8host.com/blog/nachalnaya-nastrojka-servera-debian-10/

*******
Права пользователей
sudo - ссылка с вики https://ru.wikipedia.org/wiki/Sudo
1 Перейти на суперпользователя root: su -
*******
Sudoers 
The default security policy is sudoers, which is configured via the file /private/etc/sudoers, or via LDAP.  See the Plugins section for more information.
https://www.digitalocean.com/community/tutorials/how-to-edit-the-sudoers-file-ru
Редактировать sudoers стоит только через visudo, т.к. это позволяет проверить синтаксис и корректность разрешений. 
Можно настроить дефолтный редактор sudoers с помощью команды _sudo update-alternatives --config editor_ 

Ограничения использования sudo 
- если через СУДО создать файлы или папки, или установить ПО, то текущий пользователь не получает права доступа к этим папкам, это может вести к конфликтам.
- через СУДО не срабатывают некоторые ограничения команд и сервисов, в связи с чем они могут некорректно работать. 
- у СУДО слишком много прав, поэтому можно случайно удалить систему или сделать что-то терминальное для вашей системы. 

*******
Правила для создания групп
https://losst.ru/kak-sozdat-gruppu-linux
*****
Как создать пользователя 

Чтобы создать нового пользователя по имени 8host, введите: _adduser 8host_

Как добавить пользователя в созданную группу или группу sudo 

Добавляя пользователя в эту группу, мы предоставляем ему такие же привилегии: _sudo usermod -aG sudo username_
 
Также можно использовать команду gpasswd: _sudo gpasswd -a username sudo_
*****
AppArmor
https://wiki.debian.org/AppArmor
https://gitlab.com/apparmor/apparmor/-/wikis/home

Если кратко - то это фреймворк для настройки политики безопасности, работает по папкам, и дает разные уровни доступа и прав для этих папок. 

Изначально - уже работает в Debian 10 Buster, т.е. отдельно не надо запускать. 

***** 
SSH 
Установка ssh - _sudo apt-get install ssh_

Проверка запуска _systemctl status sshd_ (запущен ssh или нет) 

Проверка порта: _cat /etc/ssh/sshd_config | grep ^Port_ 

Перезагрузка ssh: _sudo systemctl restart ssh.service_ 

Просмотр какие порты работают в OpenSSH _sudo ufw app info OpenSSH_  

Замена портов в OpenSSH - см. файл openssh-server в папке /etc/ufw/applications.d 

После замены портов нужно произвести обновление - _sudo ufw app update OpenSSH_

Проброс портов - в дополнительных настройках VB прописываем что к чему (надо добавить порт 4242)
<img width="951" alt="Screen Shot 2022-01-02 at 12 48 45 AM" src="https://user-images.githubusercontent.com/40731866/147860859-7d5812a0-5603-4020-8032-9801b7e9e1dc.png">

NAT - https://wiki.merionet.ru/seti/13/nat-na-palcax-chto-eto/
******
Как подключаться через SSH (примеры)
ssh  ufitzhug@localhost -p 2223 (2223 - Host Port)
ssh root@localhost -p 2223


*******
Установка критериев паролей на текущем пароле - _sudo chage -l ufitzhug_
