# Лабораторная работа №2


Для выполнения задания я создаю новый файл `lab2.bash`:

<img width="332" alt="Снимок экрана 2024-10-17 в 15 36 00" src="https://github.com/user-attachments/assets/add0541f-029f-4d7e-8fa8-cf9e7f75ce30">

Затем ввела команду `nаno script.bash` и  провалилась в файл:

<img width="330" alt="Снимок экрана 2024-10-17 в 15 36 35" src="https://github.com/user-attachments/assets/bfccb77c-9eed-4654-804f-62963135d2ab">

# Выполнение задания

Для начала я приняла строку, введеную пользователем, которая представляет из себя по условию задачи IP адресс , и разбила её по точке для получения 4 чисел:
- IFS='.' - устанавливаем IFS на точку. Это значит, что строка будет разбита по точкам.
- read num1 num2 num3 num4  - читаем значения , занося их в переменные 
-  <<< "$str_IP": Используем строку "$str_IP" как стандартный ввод для команды read.

<img width="332" alt="image" src="https://github.com/user-attachments/assets/116bd9c6-2842-4979-bf70-bacb8154966f">


Затем я создала функцию, которая переводит число в двоичную систему счисления:

<img width="264" alt="image" src="https://github.com/user-attachments/assets/5df472dc-c922-4fd4-951d-66a1e3152480">

Далее запустила функцию для кадого из чисел, тем самым преобразовав их в двоичную запись:

<img width="199" alt="image" src="https://github.com/user-attachments/assets/051c2fb9-738f-4670-aa6a-a393c406b7ed">

После чего сделала так , чтобы длинна каждого числа была равна 8: если длинна меньше, то заполняем нулями слева:

<img width="279" alt="image" src="https://github.com/user-attachments/assets/fd19040a-ff76-4f22-b926-449c5af5a90a">

Все полученные числа преобразовала в одну строку, разделяя их точкой, и вывела полученный результат:

<img width="442" alt="image" src="https://github.com/user-attachments/assets/c59286bc-6045-4b68-beb4-227f2f343d3b">

На примере IP адресса из условия задания запустила файл , но столкнулась с ошибкой: нет прав запускать этот файл, поэтому воспользовалась `chmod` , чтобы устранить ошибку:

<img width="394" alt="Снимок экрана 2024-10-17 в 15 27 16" src="https://github.com/user-attachments/assets/55169f94-a29b-4004-b901-9553588c9bbb">

Запустила файл заново и получила правильный результат:

<img width="506" alt="Снимок экрана 2024-10-17 в 15 34 36" src="https://github.com/user-attachments/assets/0e512ab8-b020-4a8b-86d4-e8c59a68ce0a">


Полный код задачи:
```bash
#!/bin/bash
str_IP="$@"
IFS='.' read num1 num2 num3 num4 <<< "$str_IP"
bin_func() {
  local number=$1
  local bin_num=""
  while [[ $number -gt 0 ]]; do
    local remainder=$((number % 2))
    bin_num="${remainder}${bin_num}"
    number=$((number / 2))
  done
  echo "$bin_num"
}

num_bin_1=$(bin_func $num1)
num_bin_2=$(bin_func $num2)
num_bin_3=$(bin_func $num3)
num_bin_4=$(bin_func $num4)

num_bin_1=$(printf "%08d" $num_bin_1)
num_bin_2=$(printf "%08d" $num_bin_2)
num_bin_3=$(printf "%08d" $num_bin_3)
num_bin_4=$(printf "%08d" $num_bin_4)

result="${num_bin_1}.${num_bin_2}.${num_bin_3}.${num_bin_4}"
echo "results: ${result}"

```

*Работу выполнила Федорова Мария Витальевна.*
