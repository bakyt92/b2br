Всем приветики в этом чатике

Хороший источник по этому проекту - у Ани
Тут будут заметки

Права пользователей
sudo - ссылка с вики 
1 Перейти на суперпользователя root: su -
*******
Sudoers 
https://www.digitalocean.com/community/tutorials/how-to-edit-the-sudoers-file-ru

Как добавить в группу sudo 

Добавляя пользователя в эту группу, мы предоставляем ему такие же привилегии:
sudo usermod -aG sudo username
 
Также можно использовать команду gpasswd:
sudo gpasswd -a username sudo
*******
