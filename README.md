# Отчет по лабораторной работе №1 
## дисциплина: "Операционные системы"

Студент: Рыскалова Екатерина Андреевна
###
Группа: НПМбв02-20


# Цель работы

Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

# Ход работы

1.   Установлена ОС Linux Fedora на виртуальную машину VirtualBox:


   ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/a5b5134b-8d4e-41d7-9c6d-540707a29f47)

2.   Выполнен вход в учетную запись, открыт терминал, произведено переключение на роль root-пользователя:

   
   ``` shell
    sudo -i
   ```

   ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/37fd64d8-7474-428d-b6ec-9049277b09af)

3.   Обновлены все пакеты:
   ``` shell
    dnf -y update
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/16665252-3519-489d-a810-602e67a0b70c)


4.   Установлены программы для удобства работы в консоли:
   ``` shell
    dnf -y install tmux mc
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/1ced0159-e43a-4513-8622-6a339456ece1)

5.   Установлено программное обеспечение для автоматического обновления, запущен таймер:
   ``` shell
    dnf install dnf-automatic
    systemctl enable --now dnf-automatic.timer
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/32c1b648-c6f8-4cf5-ae67-a5831ae2ffaf)


6.   Отключен SELinux
- Замена SELINUX=enforcing на значение SELINUX=permissive в файле:
   ``` shell
    /etc/selinux/config
   ```
   ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/e291c766-4ba0-49b6-8409-30a3faf81243)

- Перезагрузка виртуальной машины:
   ``` shell
    reboot
   ```
   ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/b91d1d6d-e11e-4c97-ac46-211a340d6559)

7.   Установка драйверов для VirtualBox:
- Установка средств разработки:
   ``` shell
    dnf -y group install "Development Tools"
   ```
   ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/754c73c2-84e6-4045-b309-d7b0ebd61e06)
    
- Установка пакета DKMS::
   ``` shell
    dnf -y install dkms
   ```
   ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/3108cc66-4d35-4c30-80e5-52b618f80a7d)

- В меню виртуальной машины подключен образ диска дополнений гостевой ОС.
- Диск подмонтирован:
   ``` shell
    mount /dev/sr0 /media
   ```
   ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/dcffd0a6-058b-4e80-b7bf-939d9907d50a)

- Установлены драйвера:
   ``` shell
    /media/VBoxLinuxAdditions.run
   ```
   ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/96d85b28-d851-4472-96aa-9600f9f72965)

- Перезагрузка виртуальной машины:
   ``` shell
    reboot
   ```
8.   Настройка раскладки клавиатуры:
   
- Выполнен вход в ОС под заданной вами при установке учётной записью
- Запущен терминал
- Запущен терминальный мультиплексор tmux:
   ``` shell
    tmux
   ```  
- Открыт конфигурационный файл:
  ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/d04e2d5d-8213-455f-ae28-c9453d602976)

- Отредактирован конфигурационный файл:
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/e816a3fb-ebb1-439f-9bb0-6f6677283e93)

- Перезагрузка виртуальной машины:
   ``` shell
    reboot
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/446c5bca-1cc6-4384-b138-c4604396080c)

9.   Установка имени пользователя и названия хоста

- Запущен терминальный мультиплексор tmux:
   ``` shell
    tmux
   ```
- Произведено переключение на роль root-пользователя:
   ``` shell
    sudo -i
   ```
- Создан пользователь:
   ``` shell
    adduser -G wheel earyskalova
   ```
- Задан пароль для пользователя:
   ``` shell
    passwd earyskalova
   ```
- Установлено имя хоста:
   ``` shell
    hostnamectl set-hostname earyskalova
   ```
- Проверено, что имя хоста установлено верно:
   ``` shell
    hostnamectl
   ```
 ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/146a9b60-b911-47d7-ad5e-fe074c0cba32)
   
10. Подключение общей папки
- Внутри виртуальной машины добавьте своего пользователя в группу vboxsf:
   ``` shell
    gpasswd -a earyskalova vboxsf
   ```
- В хостовой системе подключите разделяемую папку:
   ``` shell
    vboxmanage sharedfolder add "$(id -un)_os-intro" --name=work --hostpath=work --automount
   ```
- Перезагрузка виртуальной машины:
   ``` shell
    reboot
   ```
- Папка будет монтироваться в /media/sf_work.    

