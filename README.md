Всем приветики в этом чатике

Хороший источник по этому проекту - у Ани
Тут будут заметки

Права пользователей
sudo - ссылка с вики https://ru.wikipedia.org/wiki/Sudo
1 Перейти на суперпользователя root: su -
*******
Sudoers 
The default security policy is sudoers, which is configured via the file /private/etc/sudoers, or via LDAP.  See the Plugins section for more information.
https://www.digitalocean.com/community/tutorials/how-to-edit-the-sudoers-file-ru
Редактировать sudoers стоит только через visudo, т.к. это позволяет проверить синтаксис и корректность разрешений. 
Можно настроить дефолтный редактор sudoers с помощью команды _sudo update-alternatives --config editor_

Как добавить в группу sudo 

Добавляя пользователя в эту группу, мы предоставляем ему такие же привилегии:
sudo usermod -aG sudo username
 
Также можно использовать команду gpasswd:
sudo gpasswd -a username sudo
*******
fs
Для этого кстати нужно создать группу SUDO (но она фактически есть после установки SUDO)
https://losst.ru/kak-sozdat-gruppu-linux

*****
