### Устанавливаем FTP сервер в систему, попутно создавая пользователя

* `sudo apt-get install proftpd` (выбираем 'standalone' mode)
* sudo nano /etc/init.d/proftpd/proftpd.conf
* Меняем "ServerName" на какое-нибудь имя латиницей
* Меняем "UserIPv6" на "off"
* Раскоментируем (убираем знак # в начале строки) "RequireValidShell", и прописываем для этой настройки "off"
* Раскоментируем "DefaultRoot", меняем настройку на "~"
* Сохраняем файл. В nano это Ctrl+o, выйти Ctrl+x.
* Перезагружаем proftpd: `sudo /etc/init.d/proftpd restart`
* Создаем группу: `groupadd developers`, вместо developers пишем имя группы
* Добавляем пользователя: `useradd user_name --home /var/www/dirname --shell /bin/false --group developers`
* Меняем права на целевую папку пользователя: `chown user_name:developers -R /var/www/dirname`, -R означает рекурсивно.
* Меняем пароль пользователя: `sudo passwd user_name`