# Лабораторная работа №4
## Задание

## Выполнение работы

1) Cоздаем Dockerfile

   ![2024-11-15 15 05 44](https://github.com/user-attachments/assets/75a30843-7672-4fd7-ba2f-595b36d58ab9)

2) Запускаем команду для сборки образа под назавнием lab4:

   <img width="954" alt="image" src="https://github.com/user-attachments/assets/d6f467bf-e028-4bb3-8abe-705c212fae7d">

3) Создаем контейнер под названием container1 и запускаем в нём приложение aafire:

   <img width="800" alt="image" src="https://github.com/user-attachments/assets/32d8e73b-435a-4610-9432-1d06a4d7c275">
![2024-11-15 15 03 32](https://github.com/user-attachments/assets/315ba25f-6a1f-4222-a180-1249726ff95a)

4) В нвоой вкладке терминала создаем и запускаем новый контейнер под названием container2:

   <img width="631" alt="image" src="https://github.com/user-attachments/assets/8ee5d27a-eb15-480c-9528-d27f71b39aa2">

5) Содаею сеть при помощи команды:

   ```bash
   docker network create myNetwork
   ```
   <img width="587" alt="image" src="https://github.com/user-attachments/assets/b3cc5906-f3e2-47e8-a6e3-d07182d9da73">
   
6) Подключаем контейнеры к сети

    <img width="622" alt="image" src="https://github.com/user-attachments/assets/19b5f0f7-c8fa-43bd-a449-c1ee465fcd6d">

7)С помощью команды узнаем настройки сети и видим там подключенные контейнеры:

   ```bash
   docker network inspect myNetwork
   ```

  <img width="816" alt="image" src="https://github.com/user-attachments/assets/691e1b83-af55-48e7-a696-64db23fbf326">

8) Проверяем связь между контейнерами:

   <img width="604" alt="image" src="https://github.com/user-attachments/assets/3394a8a2-ebcc-46c4-8a32-c30e65695508">

   <img width="612" alt="image" src="https://github.com/user-attachments/assets/02ecaa56-d67b-493a-b8ad-8a60c4219578">

   
