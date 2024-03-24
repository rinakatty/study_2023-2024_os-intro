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
- Перезагрузка виртуальной машины:
   ``` shell
    reboot
   ```
7.   Установка драйверов для VirtualBox:
- Установка средств разработки:
   ``` shell
    dnf -y group install "Development Tools"
   ```    
- Установка пакета DKMS::
   ``` shell
    dnf -y install dkms
   ```
- В меню виртуальной машины подключите образ диска дополнений гостевой ОС.
- Диск подмонтирован:
   ``` shell
    mount /dev/sr0 /media
   ```
- Установлены драйвера:
   ``` shell
    /media/VBoxLinuxAdditions.run
   ```
- Перезагрузка виртуальной машины:
   ``` shell
    reboot
   ```




-   Каталог для лабораторных работ имеет вид `labs`.

-   Каталоги для лабораторных работ имеют вид `lab<номер>`, например: `lab01`, `lab02` и т.д.

-   Каталог для групповых проектов имеет вид `group-project`.

-   Каталог для персональных проектов имеет вид `personal-project`.

-   Если проектов несколько, то они нумеруются подобно лабораторным работам.

-   Этапы проекта обозначаются как `stage<номер>`.

# Шаблон для рабочего пространства

-   Репозиторий:
    <https://github.com/yamadharma/course-directory-student-template>.

## Сознание репозитория курса на основе шаблона

-   Репозиторий на основе шаблона можно создать либо вручную, через web-интерфейс, либо с помощью утилит `gh`.

-   Создание с помощью утилит выглядит следующим образом:

    ``` shell
    gh repo create <new-repo-name> --template="<owner/template-repo>"
    ```

-   Например, для 2023--2024 учебного года и предмета «Операционные системы» (код предмета `os-intro`) создание репозитория примет следующий вид:

    ``` shell
    mkdir -p ~/work/study/2023-2024/"Операционные системы"
    cd ~/work/study/2023-2024/"Операционные системы"
    gh repo create study_2023-2024_os-intro --template=yamadharma/course-directory-student-template --public
    git clone --recursive git@github.com:<owner>/study_2023-2024_os-intro.git os-intro
    ```

-   Сделать свой репозиторий на основе шаблона можно и вручную.

## Настройка каталога курса

-   Перейдите в каталог курса:

    ``` shell
    cd ~/work/study/2023-2024/"Операционные системы"/os-intro
    ```

-   Удалите лишние файлы:

    ``` shell
    rm package.json
    ```

-   Создайте необходимые каталоги:

    ``` shell
    echo os-intro > COURSE
    make
    ```

-   Отправьте файлы на сервер:

    ``` shell
    git add .
    git commit -am 'feat(main): make course structure'
    git push
    ```
