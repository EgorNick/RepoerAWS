# Отчет по лабораторной AWS

### Введение 
Мы брали информацию об `AWS` на официальном сайте: `https://aws.amazon.com`
Вот сервисы, которые были использованы в рамках лабораторной работы:

### AmazonElastiCache - Compute
- сервис повышает производительность веб-приложений, извлекая информацию из управляемых кешей в памяти, вместо использования дисковых баз данных.
Использование сервиса в лабораторной: `Tax` 

![Screenshot of a 1 photgr.](https://github.com/cs-itmo-2023/lab-5-EgorNick/blob/main/Report/1.jpg)

### AmazonES - Search & Analytics
- используется для поиска и хранения логов и их анализа данных.

### AmazonCloudfront - Content Delivery
- это сеть доставки контента, которая была создана для его кэширования ближе к потребителям, чтобы повысить скорость доступа к нему.
  В`Data Transfer` у нас идёт оплата за передачу данных через этот сервис.

### AmazonQLDB - Database
- используется для ведения неизменяемых данных kjgkjgjhfhgfgh
  Мы используем этот сервис для хранения данных и ввода-вывода.
  
### AWSKMS, AWSCloudHSM - Security:
AWSKMS - обеспечивает безопасность ключей для защиты данных в сервисах и приложениях AWS.
Нам потребуется использовать в таблице `KMS API Requests` (API запросы на использование KMS) и `KMS Keys Usage` (для ключей шифрования).

AWSCloudHSM - используется для более сложных требований. С помощью AWS CloudHSM можно выполнять различные криптографические задачи и т.д. Поэтому используем в таблице `HSM Operations`. 


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


