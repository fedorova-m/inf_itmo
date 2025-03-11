# Лабораторная работа №5
## Предварительные требования:

1. Основы работы с Git.
2. Установленный Git на локальной машине 
## Задание 1
<img width="783" alt="image" src="https://github.com/user-attachments/assets/cc9f3e61-caa8-4df3-866f-f3c32617a604">

#### Выполнение работы
1) создание репозитория
```
https://github.com/MashaFedorova06/inf-lab5.git
```
2) клонирование
```shell
git clone [https://github.com/MashaFedorova06/inf-lab5.git]
```
3) Создание хука pre-commit, который будет отвечать за проверку коммитов:
```shell
  cd .git/hooks
  touch pre-commit
  chmod +x pre-commit

```
<img width="1444" alt="image" src="https://github.com/user-attachments/assets/339b6108-5088-4d76-8f67-97224d2828ff">


<img width="621" alt="image" src="https://github.com/user-attachments/assets/f67e8839-b404-4b80-99d6-0132df339c9a">


<img width="671" alt="image" src="https://github.com/user-attachments/assets/fa201329-2425-4b61-8596-5ae3a8d68280">


<img width="650" alt="image" src="https://github.com/user-attachments/assets/4b8e9e59-623d-4553-9199-996f834a81c0">




4) Написание bash скрипта для проверки коммита ( должно быть слово "автор:" и не должно быть слова "NoCommit":
   
![tg_image_132047091](https://github.com/user-attachments/assets/f8c53da6-6942-448b-a4e4-df0375befce0)

5) Проверяем работу:

- правильный .txt файл:
 
   <img width="754" alt="image" src="https://github.com/user-attachments/assets/79d476b7-2e66-4c69-bfca-1c6e90559a97">
   
- нет слова "автор:":
 
  ![tg_image_2967502245 (1)](https://github.com/user-attachments/assets/5c09d377-5dc2-4e62-a4cb-c1a88dad1b64)
  
- присутствует слово "NoCommit":
 
  ![tg_image_623830213](https://github.com/user-attachments/assets/cdb3b8e5-1c42-4bf2-b661-02a2430187bb)


### Задание 2


### Выполнение работы 

  ```
  git flow init
  ```
     
  - инициализируем структуру ветвления Git Flow в текущем репозитории. При этом создаются основные ветки: develop и master, а также настраиваются правила для именования релизов и фич.

     <img width="430" alt="image" src="https://github.com/user-attachments/assets/88f206f6-80d7-4d0a-a7e4-a67b6ce1d670">

   
      ```
      git flow feature start task-management
      ```

  - запускаем новую фичу под названием task-management
    
 <img width="549" alt="image" src="https://github.com/user-attachments/assets/bcc3c9da-c20c-4655-84fb-b5da6defe92c">

   ```
    echo "print('tests passed')" > task_manager.py
   ```

  - в файл task_manager.py добавяем простой код, который выводит сообщение о том, что тесты прошли успешно.

  
      ```
      git add task_manager.py
      ```

  - файл task_manager.py добавляем в индекс для последующего коммита.

 
      ```
       git commit -m "Добавлен функционал управления задачами"
      ```

  - создаем коммит с сообщением о добавлении функционала управления задачами.

<img width="687" alt="image" src="https://github.com/user-attachments/assets/0c749632-1210-40ea-a7e8-260d1e870221">


  ```
  git flow feature finish task-management
  ```

  - завершаем работу над фичей task-management. Внесенные изменения сливаются обратно в ветку develop, а ветка фичи удаляется.
<img width="596" alt="image" src="https://github.com/user-attachments/assets/056d297a-4eb1-42cd-a3d1-7e93749be358">


      ```
       git checkout develop
      ```

  - переключаемся на основную ветку разработки develop, где будут собираться все изменения перед релизом.

  
     ```
       git flow release start v1.0.0
      ```

  - запускаем процесс создания нового релиза версии v1.0.0(Создается отдельная ветка для подготовки релиза.)
<img width="594" alt="image" src="https://github.com/user-attachments/assets/1955b667-4cb1-415d-afaf-b68d56bf7eed">

 
      ```
      echo "v1.0.0" > version.txt
      ```

  - в файл version.txt записываем номер текущей версии приложения — v1.0.0.


      ```
       git add version.txt
      ```

  -  файл version.txt добавляем в индекс для последующего коммита.

 
       ```
        git commit -m "Обновлена версия для релиза v1.0.0"
       ```

  - создаем коммит с сообщением об обновлении версии приложения до v1.0.0.
<img width="642" alt="image" src="https://github.com/user-attachments/assets/4ecdad1d-75d1-41d8-bfd3-cfce17de316c">

   
     ```
      git flow release finish v1.0.0
      ```

  - завершаем процесс релиза v1.0.0. Изменения из ветки релиза сливаются в ветки develop и master, а также создается тег для новой версии.
<img width="578" alt="image" src="https://github.com/user-attachments/assets/a5055387-0458-4371-bc6f-a70e98e5c89d">

 
       ```
       git flow hotfix start hotfix-1.0.1
       ```

  - запускаем процесс создания хотфикса под названием hotfix-1.0.1. Это необходимо для исправления критической ошибки, обнаруженной после релиза.
<img width="547" alt="image" src="https://github.com/user-attachments/assets/130474a3-59e6-4ff8-98fe-5d3e68b0b613">


      ```
       git add file_with_error.py
       ```

  - файл, содержащий ошибку, добавляем в индекс для последующего коммита.


      ```
       git commit -m "Исправлена критическая ошибка"
     ```

  - создается коммит с сообщением об исправлении критической ошибки.
<img width="623" alt="image" src="https://github.com/user-attachments/assets/19c987b9-5201-41da-b30f-aaa17188d968">

```
git flow hotfix finish hotfix-1.0.1
```
  - завершаем работу над хотфиксом, после чего изменения из ветки хотфикса сливаются в обе основные ветки: develop и main.
    <img width="590" alt="image" src="https://github.com/user-attachments/assets/ae588ac6-534a-4d9d-97a4-7795bad127c7">


    ```
     git push origin develop
     ```

  - все изменения из локальной ветки develop отправляются в удаленный репозиторий на GitHub

 <img width="503" alt="image" src="https://github.com/user-attachments/assets/09d643a5-1be2-4357-a627-2ac009863df8">

  ```
  git push origin main
   ```
  - отправка всех изменений из локальной ветки main (включая завершенный релиз)
<img width="526" alt="image" src="https://github.com/user-attachments/assets/529a6640-3eb9-4598-98e4-aae1235bd67c">


 -------------------------------------------------------------------------------------------------------


*Работу выполнила Федорова Мария Витальевна.*
