# Отчет по лабораторной работе №10(11)
## дисциплина: "Операционные системы"

Студент: Рыскалова Екатерина Андреевна
###
Группа: НПМбв02-20


# Цель работы

Изучить основы программирования в оболочке ОС UNIX. Научится писать более
сложные командные файлы с использованием логических управляющих конструкций
и циклов.

# Ход работы

1. Используя команды getopts grep, написать командный файл, который анализирует
командную строку с ключами:
– -iinputfile — прочитать данные из указанного файла;
– -ooutputfile — вывести данные в указанный файл;
– -pшаблон — указать шаблон для поиска;
– -C — различать большие и малые буквы;
– -n — выдавать номера строк.

![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/393290f5-6c3b-48b6-ac04-9c3b78886b98)

![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/ab17911e-bb1e-4abe-b5d8-cb3773fe5bb4)

2. Реализовать команду man с помощью командного файла. Изучите содержимое каталога /usr/share/man/man1. В нем находятся архивы текстовых файлов, содержащих
справку по большинству установленных в системе программ и команд. Каждый архив
можно открыть командой less сразу же просмотрев содержимое справки. Командный
файл должен получать в виде аргумента командной строки название команды и в виде
результата выдавать справку об этой команде или сообщение об отсутствии справки,
если соответствующего файла нет в каталоге man1.

![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/0dd2ca2b-01b5-499b-a8bb-99ac9fdd9b28)

![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/90f18908-419c-4ab2-9e0f-cfcb076a1961)