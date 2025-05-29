# cups-for-DE
dnf install cups
nano /etc/cups/cups-files.conf заменить printadmin на student
nano /etc/cups/cupsd.conf изменить listen на ip сервера
Заменить также на Allow all
![изображение](https://github.com/user-attachments/assets/b6e3ec9f-79a9-4e97-a4fb-f01c973d7ad4)
systemctl enable --now cups
заходим на клиенте по порту 631
вкладка администрирование логин/пароль student
добавить принтер
выбрать cups-brf -  продолжить
название по выбору - совместный доступ разрешить - продолжить
выбрать generic - продолжить
выбрать pdf printer - добавить принтер
в клиенте найти настройка принтеров - разблокировать - добавить - поиск сетевых принтеров - hq-srv - найти - выбираем наш принтер - продолжить
печатаем тестовую страницу для проверки и на сервере пишем 
scp /var/spool/cups/* student@192.168.200.2:~/
заходим на клиенте в проводник и видно тестовую страницу
