### Задание 1 

Установите Zabbix Server с веб-интерфейсом.

#### Процесс выполнения
1. Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
2. Установите PostgreSQL. Для установки достаточна та версия что есть в системном репозитороии Debian 11
3. Пользуясь конфигуратором комманд с официального сайта, составьте набор команд для установки последней версии Zabbix с поддержкой PostgreSQL и Apache
4. Выполните все необходимые команды для установки Zabbix Server и Zabbix Web Server

#### Требования к результаты 
1. Прикрепите в файл README.md скриншот авторизации в админке
2. Приложите в файл README.md текст использованных команд в GitHub

![image](https://github.com/rulezzz7373/Netology/assets/138396672/9798a749-7e65-4454-95c1-b29d11859013)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/9b937c29-9e0a-4767-a499-91966deb6f80)

Установливаем репозиторий Zabbix
# wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4+debian11_all.deb
# dpkg -i zabbix-release_6.0-4+debian11_all.deb
# apt update

Установка Zabbix сервер, веб-интерфейс
# apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts 

Создаем базу данных
su - postgres -c 'psql --command "CREATE USER zabbix WITH PASSWORD '\'123456789\'';"'
su - postgres -c 'psql --command "CREATE DATABASE zabbix OWNER zabbix;"'

На хосте Zabbix сервера импортируйте начальную схему и данные. Вам будет предложено ввести недавно созданный пароль.
# zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix

Настраеваем базу данных для Zabbix сервера
Релоктируем файл /etc/zabbix/zabbix_server.conf

DBPassword=password

Запускаем процессы Zabbix сервера и агента и настройте их запуск при загрузке ОС.

# systemctl restart zabbix-server apache2
# systemctl enable zabbix-server apache2

Задание 2
Установите Zabbix Agent на два хоста.

Процесс выполнения
Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
Установите Zabbix Agent на 2 виртмашины, одной из них может быть ваш Zabbix Server
Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов
Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera
Проверьте что в разделе Latest Data начали появляться данные с добавленных агентов
Требования к результаты
Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
Приложите в файл README.md текст использованных команд в GitHub
