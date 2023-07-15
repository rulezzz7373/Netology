# Домашнее задание к занятию «Что такое DevOps. СI/СD»


### Задание 1

**Что нужно сделать:**

1. Установите себе jenkins по инструкции из лекции или любым другим способом из официальной документации. Использовать Docker в этом задании нежелательно.
2. Установите на машину с jenkins [golang](https://golang.org/doc/install).
3. Используя свой аккаунт на GitHub, сделайте себе форк [репозитория](https://github.com/netology-code/sdvps-materials.git). В этом же репозитории находится [дополнительный материал для выполнения ДЗ](https://github.com/netology-code/sdvps-materials/blob/main/CICD/8.2-hw.md).
3. Создайте в jenkins Freestyle Project, подключите получившийся репозиторий к нему и произведите запуск тестов и сборку проекта ```go test .``` и  ```docker build .```.

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.
![image](https://github.com/rulezzz7373/Netology/assets/138396672/d9dd1731-1ba9-4d33-9b3c-ac5313ec3275)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/33f8e976-a85d-4028-b3be-1b514e8cbee8)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/f45c99dc-b12f-412b-9cce-c698b7f5bda6)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/94c7ab88-40ad-4996-aebd-f5b6234d459d)


---

### Задание 2

**Что нужно сделать:**

1. Создайте новый проект pipeline.
2. Перепишите сборку из задания 1 на declarative в виде кода.

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.
![image](https://github.com/rulezzz7373/Netology/assets/138396672/63030b99-4524-4b72-9b4a-81b65cdfcf0a)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/08440b57-5fea-4edb-a507-5348aa744971)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/a8865026-1f9e-4c41-81bd-229e41042247)

---

### Задание 3

**Что нужно сделать:**

1. Установите на машину Nexus.
1. Создайте raw-hosted репозиторий.
1. Измените pipeline так, чтобы вместо Docker-образа собирался бинарный go-файл. Команду можно скопировать из Dockerfile.
1. Загрузите файл в репозиторий с помощью jenkins.

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.
![image](https://github.com/rulezzz7373/Netology/assets/138396672/55fdc0df-ddcb-4012-82db-faa88f625b8e)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/bc0045ce-b83e-44c9-b6fd-66eb6152d49c)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/2fdf44b6-fd6b-4760-8e23-b4e055c2911b)
![image](https://github.com/rulezzz7373/Netology/assets/138396672/93fab1b1-b089-4309-b1d1-4b8c87eca330)





