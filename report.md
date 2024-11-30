# Отчет по лабораторной работе №5

### Введение 
Сначала я создал репозиторий git-practice на GitHub и скопировал его URL-адрес
Далее с помощью терминала и команд `git clone` и `cd` я перешёл в папку для локального сохранения репозитория. Потом я создал новый текстовый файл example.txt, а дальше добавил в него некоторый текст и запушил на GitHub в основуную ветку main, используя команды `git add, git commit -m и git push origin main`. 

![Screenshot of a 1 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/1.jpg)

Затем создал новую ветку feature branch с помощью команды `git branch`, переключился на нее с помощью `git checkout`. После я отредактировал файл example.txt, повторил некоторые шаги из пункта 3,
![Screenshot of a 1 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/19.jpg)

Потом переключился обратно в основную ветку main помощью `git checkout main` и слил изменения из feature branch в основную ветку, а затем сохранил структуру файла, используя `git merge feature branch и git push origin main`.

![Screenshot of 2 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/2.jpg)

### Работа с ветками: 
Я создал новый текстовый файл с базовой структурой книги book.txt. С помощью git checkout -b создал новую ветку feature-login.

Далее я внёс изменения в файл, закоммитил их и отправил ветку на GitHub, используя `git add, git commit -m, git push origin`.

![Screenshot of 3 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/3.jpg)
![Screenshot of 4 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/4.jpg)

### Работа с удаленным репозиторем: 
Я переключился на основную ветку main, внёс изменения в файл и закоммитил изменения и отправил их на GitHub с помощью `git add, git commit -m, git push origin`. 

![Screenshot of 5 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/5.jpg)
  
### Моделирование конфликта: 
Я вернулся в ветку feature-login, изменил главу 2 в файле, закоммитил изменения и отправил их на GitHub, используя `git checkout, git add, git commit -m, git push origin feature login`.

![Screenshot of 5 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/6.jpg)

### Разрешение Нашего конфликта:
Я вернулся в основную ветку main и попробовал слить изменения с помощью `git checkout main и git merge feature-login`. Возник у меня конфликт.   

![Screenshot of 6 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/7.jpg)

Я разрешил конфликт, удалив метки и оставив нужные изменения. Я закоммитил решение конфликта и отправил его на GitHub с помощью `git add, git commit -m, git push origin main`. 

![Screenshot of 8 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/8.jpg)

### Автоматизация проверки формата файлов при коммите 
- Я создал bash-script, который будет выполнять проверку формата .txt файлов.
Я добавил мой скрипт в репозиторий, поместив его в папку .git/hooks и убедившись, что у него есть права на выполнение с помощью cp и chmod +x.

![Screenshot of 9 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/1_1.jpg)
![Screenshot of 11 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/9.jpg)

 Далее я попробовал внести изменения и закоммитить. Теперь, при каждой попытке закоммитить изменения, Git будет автоматически выполнять проверку формата файлов перед коммитом. При возникновении необходимости внести изменения в файлы, чтобы они соответствовали формату, нужно внести изменения, добавить файлы и снова попробовать закоммитить.

 ![Screenshot of 10 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/10.jpg)

### Использование Git Flow в проекте: 
Сначала я проверил, есть ли у меня на нашем устройстве утилита Git Flow. Затем я выполнил инициализацию Git Flow в корне репозитория с помощью `git flow init`.

 ![Screenshot of 10 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/flow_init.jpg)

Создал ветку для новой функциональности "task-management" с помощью `git flow feature start task-management`. Внёс изменения в код для добавления функционала управления задачами task_manager.py и выполнил коммит.

 ![Screenshot of 10 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/task_managment.jpg)

Потом я завершил фичу с помощью `git flow feature finish task-management`.

 ![Screenshot of 10 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/finish_task.jpg)

Далее  начал создание релиза: 
```
git flow release start v1.0.0
```

 ![Screenshot of 10 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/release_start.jpg)

Я внёс изменения, связанные с релизом: 
```
echo "v1.0.0" > version.txt

git add version.txt

git commit -m "Обновлена версия для релиза v1.0.0"
```

![Screenshot of 7 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/12.jpg)

Мы завершаем релиз и объединяем его с ветками develop и main: `git flow release finish v1.0.0`,


![Screenshot of 10 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/release_finish.jpg)

Внёс изменения для исправления ошибки и закоммитил их: 
```
git add file_with_error.py

git commit -m "Исправлена критическая ошибка"
```

![Screenshot of 7 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/13.jpg)

Завершил я затем hotfix и объединил его с ветками develop и main: `git flow hotfix finish hotfix-1.0.1`/

 ![Screenshot of 10 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/hotfix_fins.jpg)

Отправил изменения на удаленный репозиторий:

![Screenshot of 11 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/14.jpg)

![Screenshot of lending photo](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/ending.jpg)


