# Git Cheatsheet

Git - это одна из самы популярных систем контроля версий. Ниже представлены основные команды для использования git.

## Первоначальная настройка

Настройка информации о пользователе для всех локальных репозиториев

Устанавливает имя автора коммитов:

```bash
$ git config --global user.name "[name]"
```

___

Устанавливает адрес электронной почты автора коммитов:

```bash
$ git config --global user.email "[email]"
```

## Создание репозитория

Создаёт новый локальный репозиторий с заданным именем:

```bash
$ git init [project name]
```

___

Скачивает репозиторий вместе со всей его историей изменений:

```bash
$ git clone [url address]
```

## Внесение изменений

Перечисляет все новые или изменённые файлы, которые нуждаются в фиксации:

```bash
$ git status
```

___

Индексирует указанный файл для последующего коммита:

```bash
$ git add [file]
```

___

Индексирует все файлы в директории репозитория для последующего коммита:

```bash
$ git add --all
# or
$ git add .
```

___

Фиксирует проиндексированные изменения и сохраняет их в историю версий:

```bash
$ git commit -m "[message]"
```

___

История коммитов для текущей ветки:

```bash
$ git log
```

## Работа с удаленным репозиторием

Привязывает удалённый репозиторий к локальному:

```bash
$ git remote add [remote name] [remote repository url]
```

___

Показывает все удаленные репозитории:

```bash
$ git remote -v
```

___

Загружает все изменения локальной ветки в ветку удалённого репозитория и связывает их (ветки):

```bash
$ git push -u [remote name] [branch name]
```

___

Загружает все изменения локальной ветки в ветку удалённого репозитория, если они уже были связаны ранее:

```bash
$ git push
```

## Хэш, `git log`, HEAD

### Хэш

Хэш - это уникальный идентификатор коммита в Git.
По нему можно узнать всю основную информацию о коммите. Git хеширует эту информацию с помощью алгоритма SHA-1 и хранит таблицу соответствия хэш -> информция о коммите в папке `./.git`.

Хэш состоит из цифр 0—9 и латинских букв A—F и обладает следующими важными свойствами:
- для одного и того же набора данных хэш всегда одинаковый;
- при изменении исходных данных хеш тоже изменится (причём сильно).

### `git log`

Печатает список коммитов с их описанием:
- Хэш коммита.
- Author — имя автора и его электронная почта.
- Date — дата и время создания коммита.
- Сообщение к коммиту.

```bash
$ git log
```

Пример вывода:

```bash
commit e4b95659b8a2189c046b935b53faa15e339116ab (HEAD -> main)
Author: vpopi4 <vpopi4@yandex.ru>
Date:   Sat Apr 13 04:57:20 2024 +0300

    feat: add hash information

commit 95388f344f97b40cce400512691688ca5a540f81
Author: vpopi4 <vpopi4@yandex.ru>
Date:   Sat Apr 13 04:54:56 2024 +0300

    refactor: add separating lines between command description

commit e8b9b1ba833efa2a54d74afa0ba031b3a3a0fc51 (origin/main)
Author: Cyrill <vpopi4@ya.ru>
Date:   Wed Jan 24 23:26:46 2024 +0300

    added to README.md file a cheat sheet on using git

```

___

Печатает в одну строку сокращенный лог:
- Сокращенный хэш - несколько первых символов хэша, alias хэша, длину определяет git
- Первая строка комментария.

```bash
$ git log --oneline
```

Пример: 

```bash
e4b9565 (HEAD -> main) feat: add hash information
95388f3 refactor: add separating lines between command description
e8b9b1b (origin/main) added to README.md file a cheat sheet on using git

```
