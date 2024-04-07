# Отчет по лабораторной работе №3 
## дисциплина: "Операционные системы"

Студент: Рыскалова Екатерина Андреевна
###
Группа: НПМбв02-20


# Цель работы

Ознакомление с файловой системой Linux, её структурой, именами и содержанием
каталогов. Приобретение практических навыков по применению команд для работы
с файлами и каталогами, по управлению процессами (и работами), по проверке использования диска и обслуживанию файловой системы.


# Ход работы

1. Копирование файла в текущем каталоге. Скопировать файл ~/abc1 в файл april
и в файл may:
   ``` shell
    cd
    touch abc1
    cp abc1 april
    cp abc1 may
   ```
   ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/634aba3b-26cc-4515-b598-5b7f8fec2b6c)

 2. Копирование нескольких файлов в каталог. Скопировать файлы april и may в каталог
monthly:
   ``` shell
    mkdir monthly
    cp april may monthly
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/9414c929-831f-42bf-aba7-988108c321a9)

3. Копирование файлов в произвольном каталоге.Скопировать файл monthly/may в файл
с именем june:
   ``` shell
    cp monthly/may monthly/june
    ls monthly
   ```
   ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/e5ec7fad-1272-4787-b5e3-a9cffba5948f)

4. Копирование каталогов в текущем каталоге. Скопировать каталог monthly в каталог
monthly.00:
   ``` shell
    mkdir monthly.00
    cp -r monthly monthly.00
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/43ba3bb1-00cc-4035-bd7b-2a31a38ec4da)


   
