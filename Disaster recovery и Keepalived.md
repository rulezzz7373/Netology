# Домашнее задание к занятию 1 «Disaster recovery и Keepalived»

### Задание 1
- Дана [схема](1/hsrp_advanced.pkt) для Cisco Packet Tracer, рассматриваемая в лекции.
- На данной схеме уже настроено отслеживание интерфейсов маршрутизаторов Gi0/1 (для нулевой группы)
- Необходимо аналогично настроить отслеживание состояния интерфейсов Gi0/0 (для первой группы).
- Для проверки корректности настройки, разорвите один из кабелей между одним из маршрутизаторов и Switch0 и запустите ping между PC0 и Server0.
- На проверку отправьте получившуюся схему в формате pkt и скриншот, где виден процесс настройки маршрутизатора.https://github.com/rulezzz7373/Netology/blob/main/hsrp_advanced_shkurko.pkt
![image](https://github.com/rulezzz7373/Netology/assets/138396672/c8887074-0700-4a17-86a4-49e790bfc51d)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/6688d0ca-bc35-423a-9b13-7ee54a24dca0)



------


### Задание 2
- Запустите две виртуальные машины Linux, установите и настройте сервис Keepalived как в лекции, используя пример конфигурационного [файла](1/keepalived-simple.conf).
- Настройте любой веб-сервер (например, nginx или simple python server) на двух виртуальных машинах
- Напишите Bash-скрипт, который будет проверять доступность порта данного веб-сервера и существование файла index.html в root-директории данного веб-сервера.
- Настройте Keepalived так, чтобы он запускал данный скрипт каждые 3 секунды и переносил виртуальный IP на другой сервер, если bash-скрипт завершался с кодом, отличным от нуля (то есть порт веб-сервера был недоступен или отсутствовал index.html). Используйте для этого секцию vrrp_script
- На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived, а также скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html

Скрипт ([[ -f '/var/www/html/index.nginx-debian.html' ]]) && (killall -0 nginx 2> /dev/null)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/8e69d9d0-9396-47c4-83ac-03582270bc16)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/90769f04-c64b-4051-a963-8c71cb89b114)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/52f78c7c-d98d-4973-9d1d-e975e1df1d9f)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/6243dca3-0749-4621-a1da-60660b6b4c7c)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/ebf95a10-c348-4b41-8087-4d8d06def5bc)
