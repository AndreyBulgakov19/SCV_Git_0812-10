# Репозиторий для **pull request**
* В своём аккаунте на GitHub создать копию репозитория **"AndreyBulgakov19
/SCV_Git_2110"** с помощью кнопки **"Fork"**.
---
* Клонировать копию репозитория на локальный компьютер.
---
* Создать новую ветку.
---
* Добавить файл с инструкцией в новую ветку.
---
* Дополнить инструкцию разделами по работе с удалёнными репозиториями, pull request.
---
* Зафиксировать изменения (коммиты).
---
* Отправить изменения на GitHub.
---
* На сайте GitHub выполнить **Pull request**.
---

![logo](Temp\3221.jpeg)
# Работа с Git
## 1. Проверка наличия установленного Git.
В терменале выполнить команду `Git version`.

Если Git установлен, появится сообщение с информацией о версии программы. Иначе будет сообщение об ошибке.

## 2. Установка Git.
Загружаем последнюю версию Git с сайта https://git-scm.com/downloads.
Устанавливаем с настройками по умолчанию.

## 3. Настройка Git.
При первом использовании Git необходимо представиться. Для этого в терминале нужно выполнить две команды: 
```
git config --global user.name "Ваше имя английскими буквами"
git config --global user.emale ваша почта2example.com
``` 

## 4. Инициализация Репозитория.
Получить репозиторий можно двумя способами.

1. В терминале переходим к папке, в которой хотим создать репозиторий. Выполняем команду 
```
git init
```
2. Клонировать существующий репозиторий Git из любого места. Сделть это можно так: 
```
git clone <адрес репозитория>
```

## 5. Запись изменений в Репозитории.

Перед созданием нового комита необходимо добавить к отслеживанию файлы. Эта операция выполняедся командой `git add "name"` или `git add .` в случае если необходимо добавить все файлы в репозитории.

Для проверки статуса файлов в репозитории выполняется команда `git status` - она выводит в консоли данные о состаянии репозитория, отслеживаемых файлов, текущих ветке и комите.

```
git commit - m "коментарий к текущему комиту"
```
Для оптимизации рабочего процесса можно использовать следущую команду:

```
git commit - am "коментарий к текущему комиту"
```
Она включает в себя `gid add`, добавляя все файлы в репозитории и создавая новый комит. Данная команда не работает для новых файлов.

Для отображения изменений между текущим и закомиченным файлами используется команда   `git diff`. Она выводит в консоли список измененных, добавленных и удаленых строк.
Для перевода консоли из командного режима обратно в текстовый необходимо ввести `Q`

## 6. Просмотр истории коммитов.
Для вывода  списка созданных комитов используется команда `git log` 

```
commit 3f8740b48b78d48934169db9684fcede68fc3ece (HEAD -> master)
Author: Дмитрий <matveev_dmitriy1996@mail.ru>
Date:   Mon Dec 5 15:26:43 2022 +0300

    Исправление опечаток

commit 0ed85ca3e7977597cb7e86719e217aa9d8c46f9c
Author: Дмитрий <matveev_dmitriy1996@mail.ru>
Date:   Mon Dec 5 13:13:23 2022 +0300

    добавлены абзацы №2 и №3
```

или `git log --oneline` для вывода более компактного списка.

```
3f8740b (HEAD -> master) Исправление опечаток
0ed85ca добавлены абзацы №2 и №3
```

## 7. Перемещение между сохранениями

Для перемещения между комитами используется команда `git checkout "hashcode"` 

*hashcode - первые 4 символа кода см. главу 6.*


Возврат к актуальной версии осуществляется при помощи команд:

`git switch -` или  `git switch master`.

## 8. Игнорирование файлов.
Для того что бы исключить из отслеживания в репозитории файлы и папки необходимо создать там файл ***.gitgnore*** и записать в нем названия или шаблоны, соответствующие таким файлам и папкам.

![Error 404](Temp\Исключения.JPG)

## 9. Создание веток в Git.
 Ветка в Git - это простой перемещаемый указатель на один из коммитов, обычно последний в цепочке коммитов.
 Поумолчанию имя основной ветки в Git - master.

Создать ветку можно несколькмими способами:
* Командой "Создания".
* Слиянием уже существующих веток. 

 ```
 git branch <имя новой ветки>
 ```
 В результате создается новый указатель на текущий комит.

 Так же можно воспользоваться командой:
 
 ```
git checkout -b <branch_name>
 ```
В отличае от предыдущей, данная команда сразу же переключает на новую ветку.


Слияние двух веток происходит по выполнению команды:
```
git merge <branch#2_name>
```
В результате выполнения данной команды текущая ветка сливается с `<branch#2_name>`, после чего программа предлагает в ручную исправить образовавшиеся конфликты, в случае их наличия. Обе ветки остаются в списке.

В зависисости от условий используются различные команды для отменения слияния веток

```
git reset --merge
git merge --abort
git revert <hash>
```
где `<hash>` - это хэш коммита, изменения которого необходимо отменить (это отменяет изменения конкретного коммита).

В случае если был создан комит слияния, необходимо выполнить откат. 
```
git reset --hard HEAD^
```
Данная команда удаляет последний созданный комит, разделяя объедененные ветки.

После слияния неиспользуемую ветвь можно удалить командой
```
git branch -d <branch_name>
```

git reset --abort

## 10. Работа со своим удаленнымм репозиторием.

1. Создать аккаунт на Github
2. Создать локальный репозиторий

    *См. 4. Инициализация Репозитория.*
3. Связать удалённый репозторий с локальным.

   По умолчанию основная ветка в Studio visual code назвается `master`, для работы с Github необходимо переименовать её в `main`.
   
   ```
    git branch -M main
    ```
    Команда для связывания локального репозитория с удаленным:
    ```
    git remote add origin <https://github.com/.../... .git>
    ```
    
    Команда, проверяющая наличие связи между репозиториями и указывающая адреса извлечения и закачки файлов:
    ```
    git remote -v
    ```
    Данная команда, необходимая при первом *push* позволяет загрузить изменения с локального репозитория в удаленный:
    ```
    git push -u origin main 
    ```

*Перед выполнением следущюих команд необходимо убедиться в том что все изменения были закомичены и названия веток совподают:*

Загружает изменения из локального репозитория в удаленный.
```
git push
``` 


Данная комбинированная команда выкачивает файлы из удаленного репозитория и обьеденяет (выполняет `merge`) с текущим.
```
git pull 
```



## 11. "Вилки"
Для работы с чужими репозиториями используются так называемые вилки (fork). Это копия репозитория, автором которого мы не являемся, и в которую можно вносить изменения.

```
git clone <Адрес> 
```

![Ой! Тут была картинка(](Temp\Адрес.JPG)
Опционально можно изменить название файла введя свое `Name`
```
git clone <Адрес> <Name>
```

`Адрес` - берется из личного кабинета, на Github.
Для его получения необходимо создать `fork`, и копировать сылку на него из соответствующей строки. Там же можно и поменять имя скачиваемого фаила.

Если в проэкте до этого были открыты другие файлы, то для работы c клонированным файлом необходимо изменить директорию.

```
cd <Name/>
```
Где `Name` - на звание папки.

Текущую корневую папку можно узнать из консоли:
![Ой! Тут была картинка(](Temp\КорневаяПапка.png)

Перед отправкой файла необходимо закомитить изменения, проверить расположение ветки (отправляется текущая) и наличие связи между репозиториями:
```
 git remote -v
```


Перед первой отправкой, в случае если ветка с таким названием отсутствуют, необходимо выполнить одну из команд:
```
git push --set upstream origin <branch_name>
git push -u origin <branch_name>
```