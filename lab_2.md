# Отчет по лабораторной работе №2 
## дисциплина: "Операционные системы"

Студент: Рыскалова Екатерина Андреевна
###
Группа: НПМбв02-20


# Цель работы

- Изучить идеологию и применение средств контроля версий.
- Освоить умения по работе с git.

# Ход работы

1.   Установка git
   ``` shell
    dnf install git
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/3285fc9b-fdea-4cc6-af12-bd1123802d65)

2.   Установка gh
   ``` shell
    dnf install gh
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/21933a87-b4bf-4b09-b5b9-41b644313010)

3.   Базовая настройка git
- Зададим имя и email владельца репозитория:
   ``` shell
    git config --global user.name "Name Surname"
    git config --global user.email "work@mail"
   ```
- Настроим utf-8 в выводе сообщений git:
   ``` shell
    git config --global core.quotepath false
   ```
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/d1e56aa0-75d7-4e31-b363-c5bfa2790d22)

- Настройте верификацию и подписание коммитов git (см. Верификация коммитов git с помощью GPG).
   ``` shell
    gpg --full-generate-key
   ```
  ![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/e876fb0d-c159-46aa-b56d-16a5116c56a3)
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/dc937fa0-7d2a-4d5b-91de-b7be1734f977)
![image](https://github.com/rinakatty/study_2023-2024_os-intro/assets/160457049/6f111647-256b-4293-ab28-f594dd196204)


- Зададим имя начальной ветки (будем называть её master):
   ``` shell
    git config --global init.defaultBranch master
   ```

- Параметр autocrlf:
   ``` shell
    git config --global core.autocrlf input
   ```

- Параметр safecrlf:
   ``` shell
    git config --global core.safecrlf warn
   ```

4.   
5.   
   
