# Отчет по лабораторной работе №4
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

5. Копирование каталогов в произвольном каталоге. Скопировать каталог monthly.00
в каталог /tmp:
   ``` shell
    cp -r monthly.00 /tmp
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/153c1b73-3e33-4f6f-aefe-3a71e0a70526)

## Перемещение и переименование файлов и каталогов

1. Переименование файлов в текущем каталоге. Изменить название файла april на
july в домашнем каталоге:
   ``` shell
    cd
    mv april july
   ```
2. Перемещение файлов в другой каталог. Переместить файл july в каталог monthly.00:
   ``` shell
    mv july monthly.00
    ls monthly.00
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/a1d3ad2f-194c-410f-b794-084c4c0d473e)

3. Переименование каталогов в текущем каталоге. Переименовать каталог monthly.00
в monthly.01
   ``` shell
    mv monthly.00 monthly.010
   ```
4. Перемещение каталога в другой каталог. Переместить каталог monthly.01в каталог
reports:
   ``` shell
    mkdir reports
    mv monthly.01 reports
   ```
5. Переименование каталога, не являющегося текущим. Переименовать каталог
reports/monthly.01 в reports/monthly:
   ``` shell
    mv reports/monthly.01 reports/monthly
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/cbb1f667-9492-417d-be98-fa694cf58e7d)


## Права доступа

1. Требуется создать файл ~/may с правом выполнения для владельца:
   ``` shell
    cd
    touch may
    ls -l may
    chmod u+x may
    ls -l may
   ```
2. Требуется лишить владельца файла ~/may права на выполнение:
   ``` shell
    chmod u-x may
    ls -l may
   ```
3. Требуется создать каталог monthly с запретом на чтение для членов группы и всех
остальных пользователей:
   ``` shell
    cd
    mkdir monthly
    chmod g-r, o-r monthly
   ```
4. Требуется создать файл ~/abc1 с правом записи для членов группы:
   ``` shell
    cd
    touch abc1
    chmod g+w abc1
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/dfaa9803-b45f-4d47-991a-cfa198340535)

## Ход работы

1. Скопируйте файл /usr/include/sys/io.h в домашний каталог и назовите его
equipment. Если файла io.h нет, то используйте любой другой файл в каталоге
/usr/include/sys/ вместо него.

![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/e18a90a3-04d0-4cb8-8951-40c823a2c19b)

![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/5a004533-eeb4-4034-9130-fdee6873e8e6)
   

2. В домашнем каталоге создайте директорию ~/ski.plases.
3. Переместите файл equipment в каталог ~/ski.plases.
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/6edd2812-8d77-4160-9482-402426f52d97)/~
4. Переименуйте файл ~/ski.plases/equipment в ~/ski.plases/equiplist.
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/a5a148d9-0824-4f3d-9937-adcabc6d44fd)

5. Создайте в домашнем каталоге файл abc1 и скопируйте его в каталог
~/ski.plases, назовите его equiplist2.
6. Создайте каталог с именем equipment в каталоге ~/ski.plases.
7. Переместите файлы ~/ski.plases/equiplist и equiplist2 в каталог
~/ski.plases/equipment.
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/01f9e99e-de79-46d2-bb5b-a877fce98b77)

8. Создайте и переместите каталог ~/newdir в каталог ~/ski.plases и назовите
его plans.
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/5bf7d086-5da5-436b-89c9-d118213b7f52)
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/3cbf3fea-3a97-4b41-bb80-024e92aa3185)

9. Определите опции команды chmod, необходимые для того, чтобы присвоить перечисленным ниже файлам выделенные права доступа, считая, что в начале таких прав
нет:
9.1. drwxr--r-- ... australia
9.2. drwx--x--x ... play
9.3. -r-xr--r-- ... my_os
9.4. -rw-rw-r-- ... feathers
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/d2e3d71b-4595-45f2-b48d-7138d7728dfe)
   





   
   
