# Working with Remotes

Guide to working with remotes. Russian edition.

---

Для совместной работы над проектами Git требуются навыки управления удаленными репозиториями. Удаленные репозитории представляют собой версии проекта, хранимые в Интернете или где-то в сети. Их может быть несколько, и каждый в общем случае доступен вам только для чтения или же для чтения и записи.  

Взаимодействие с другими пользователями предполагает управление удалёнными репозиториями, а также отправку и получение данных из них. Управление репозиториями включает в себя как умение добавлять новые, так и умение удалять устаревшие репозитории, а также умение управлять различными удалёнными ветками, объявлять их отслеживаемыми или нет и так далее.

## Отображение удаленных репозиториев (git remote)

Просмотр уже настроенных удаленных серверов осуществляется командой **git remote**. Она дает список коротких имен для всех указанных вами областей удаленной работы. Если репозиторий был клонирован, вы должны увидеть по крайней мере источник, то есть имя, которое Git по умолчанию присваивает клонируемому серверу:

    $ git clone https://github.com/schacon/ticgit
    Cloning into 'ticgit'...
    remote: Reusing existing pack: 1857, done.
    remote: Total 1857 (delta 0), reused 0 (delta 0)
    Receiving objects: 100% (1857/1857), 374.35 KiB | 268.00 KiB/s, done.
    Resolving deltas: 100% (772/772), done.
    Checking connectivity... done.
    $ cd ticgit
    $ git remote
    origin

Параметр **-v** позволяет увидеть URL-адреса, которые Git хранит для сокращенного имени, используемого при чтении из данного удаленного репозитория и при записи в него:

    $ git remote -v
    Origin https://github.com/schacon/ticgit (fetch)
    Origin https://github.com/schacon/ticgit (push)

Если репозиториев несколько, они выводятся списком. Скажем, репозиторий с несколькими удаленными копиями для совместной работы с коллегами может выглядеть следующим образом:

    $ git remote -v
    bakkdoor https://github.com/bakkdoor/grit (fetch)
    bakkdoor https://github.com/bakkdoor/grit (push)
    cho45 https://github.com/cho45/grit (fetch)
    cho45 https://github.com/cho45/grit (push)
    defunkt https://github.com/defunkt/grit (fetch)
    defunkt https://github.com/defunkt/grit (push)
    koke git://github.com/koke/grit.git (fetch)
    koke git://github.com/koke/grit.git (push)
    origin git@github.com:mojombo/grit.git (fetch)
    origin git@github.com:mojombo/grit.git (push)

Это означает, что мы легко можем скачать себе изменения, внесенные любым из этих пользователей.

## Добавление удаленных репозиториев (git remote add)

Чтобы добавить такой репозиторий под коротким именем, которое упростит дальнейшие обращения к нему, используйте команду **git remote add [сокращенное имя] [url]**:

    $ git remote add pb https://github.com/paulboone/ticgit
    $ git remote -v
    origin https://github.com/schacon/ticgit (fetch)
    origin https://github.com/schacon/ticgit (push)
    pb https://github.com/paulboone/ticgit (fetch)
    pb https://github.com/paulboone/ticgit (push)

Теперь вместо полного URL-адреса в командную строку можно вводить имя pb. К примеру, для скачивания всей информации, которая есть у коллеги, но отсутствует у вас, используйте команду **git fetch pb**:

    $ git fetch pb
    remote: Counting objects: 43, done.
    remote: Compressing objects: 100% (36/36), done.
    remote: Total 43 (delta 10), reused 31 (delta 5)
    Unpacking objects: 100% (43/43), done.
    From https://github.com/paulboone/ticgit
    * [new branch] master -> pb/master
    * [new branch] ticgit -> pb/ticgit

Ветка master этого коллеги теперь доступна вам локально как pb/master. Вы можете выполнить ее слияние с одной из ваших веток или перейти в нее, если требуется просто проверить ее содержимое.

Для того, чтобы добавить удалённый репозиторий и присвоить ему имя (shortname), просто выполните команду **git remote add (shortname) (url)**:

## Извлечение данных из удаленных репозиториев

## Отправка данных в удаленный репозиторий

## Просмотр удаленных репозиториев

## Удаление и переименование удаленных репозиториев

