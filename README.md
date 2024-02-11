# Как сохранить версии своих файлы с помощью git
### Сохренение локально
1. Скачать [git](https://git-scm.com/download/win) и устнаовить
2. Открыть приложение git Bash
3. С помощью команды *cd* перемистить в нужную папку (можно создать папку с помощью *mkdir*)
4. Инициализировать репозиторий - *git init*
5. Создать или добавить файлы в папку репозитория. С помощью консоли это можно сделать с помощью команда *touch* - создание, *mv* - перемещение, *cp* - копирование
6. Подготовить файлы к комииту с помощью команды *git add "файл"*. Все файлы можно подготовить написав вместо файла "."
7. Сделать коммит - *git commit -m "название". **Файлы сохранены локально**
----
### Удаленное сохранение
1. Зарегистроваться на сайте [github](https://github.com)
2. Создать удаленный репозиторий с логичным именем
3. Далее с помощью команды *ssh-keygen -t ed25519 -c "потча"* генируем ключ. Для незащищенного везде нажимаем *enter*. Иначе после первого *enter* пишем ключевое слово.
4. Полученный ключ вставляем на сайте github в вкладе *Параметры*-*SSH and GPG keys*
5. Далее на вкладе созданного удаленного репозитория копируем его *ssh-адрес*
6. С помощью команды *git remote add "название удаленого репозитория" "ssh-адрес"* подкючаемся к удаленного репозитория. Проверить статус можно с помощью *git remote -v*
7. Чтобы отправить коммит на удаленный репозиторий, используем команду *git push -u "навзание удаленого репозитория" "main/master"(в зависимости, что написано в строке адреса)*. **Файлы сохранены удаленно**

----

## Работа с log

**Хеширование** (от англ. hash, «рубить», «крошить», «мешанина») — это способ преобразовать набор данных и получить их *«отпечаток»* (англ. fingerprint).

**Информация о коммите** — это набор данных: когда был сделан коммит, содержимое файлов в репозитории на момент коммита и ссылка на предыдущий, или родительский (англ. parent), коммит.

Git хеширует (преобразует) информацию о коммите с помощью алгоритма SHA-1 (от англ. Secure Hash Algorithm — «безопасный алгоритм хеширования») и получает для каждого коммита свой **уникальный хеш** — результат хеширования.

**HEAD** - это файл в папке .git, в котором записана ссылка (или ссылка на ссылку) на последний коммит.

----

## Статус файло

* **untracked** - неотслеживаемый
* **tracked** - Состояние tracked — это противоположность untracked. Оно довольно широкое по смыслу: в него попадают файлы, которые уже были зафиксированы с помощью git commit, а также файлы, которые были добавлены в staging area командой git add. То есть все файлы, в которых Git так или иначе отслеживает изменения.
* **staged** -После выполнения команды git add файл попадает в staging area (от англ. stage — «сцена», «этап [процесса]» и area — «область»), то есть в список файлов, которые войдут в коммит. В этот момент файл находится в состоянии staged.
* **modified** -Состояние modified означает, что Git сравнил содержимое файла с последней сохранённой версией и нашёл отличия. Например, файл был закоммичен и после этого изменён.

----

## Оформление коммитов

**Общие требования:**
* краткость
* информативность
* единобразие

**Стили оформления
* **Корпативный** - "*номер задачи*: *расшифровка*" 
* **Conventional Commits** - "*тип изменения*: *суть изменения*" 
* **GitHub-стиль** - "*тип изменения* *#номер*, *расшифровка*"

## Полезные команды

* **cd** - смена директори
* **pwd** - текущая директория
* **ls** - содержимое директории
* **cp** - копирование файла
* **mv** - перемещение файла
* **rm** - удаление файла
* **mkdir** - создание директории
* **touch** - создание файла
* **help** - справка по команда
* **git** - справка по командам git
* **git init** - инициализация локального репозитория
* **git status** - статут репозитория (какие файлы готовы к коммиту, нужен ли коммит)
* **git add** - подготовкка файлов к комииту
* **git restore** - убрать файл их подготовки к комииту
* **git commit** -создание коммита (сохранение данных файла)
* **ssh-keygen -t** - генерация ключа синхронизации
* **git remote add** - подключение к удаленному репозиторию
* **git remote remove** - отключени от удаленного репозитория
* **git remote -v** - статус подключения к удаленному репозиторию
* **git push -m** - отправление коммитов на удаленный репозиторий
* **git branch -M main** - смена названия ветки
* **git log --oneline** - краткая запись лога
