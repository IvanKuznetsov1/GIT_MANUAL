[На главную.](readme.md)

Отправка изменений на сервер.
---
---
Этот процесс происходит каждый раз, когда мы хотим обновить данные в удаленном репозитории.
Команда, предназначенная для этого - push. Она принимает два параметра: имя удаленного репозитория (мы назвали наш origin) и ветку, в которую необходимо внести изменения (master — это ветка по умолчанию для всех репозиториев). Например:

    $ git push origin master
    Counting objects: 3, done.
    Writing objects: 100% (3/3), 212 bytes | 0 bytes/s, done.
    Total 3 (delta 0), reused 0 (delta 0)
    To https://github.com/tutorialzine/awesome-project.git
    * [new branch] master -> master

Эта команда немного похожа на git fetch, с той лишь разницей, что при помощи fetch мы импортируем коммиты в локальную ветку, а при применив push, мы экспортируем их из локальной в удаленную. Если вам необходимо настроить удаленную ветку используйте git remote. Однако пушить надо осторожно, ведь рассматриваемая команда перезаписывает безвозвратно все изменения. В большинстве случаев, ее используют, чтобы опубликовать выгружаемые локальные изменения в центральный репозиторий. А еще ее применяют для того, чтобы поделиться, внесенными в локальный репозиторий, нововведениями, с коллегами или другими удаленными участниками разработки проекта. Подытожив сказанное, можно назвать git push - командой выгрузки, а git pull и git fetch - командами загрузки или скачивания. После того как вы успешно запушили измененные данные, их необходимо внедрить или интегрировать, при помощи команды слияния git merge.
В зависимости от сервиса, который вы используете, вам может потребоваться аутентифицироваться, чтобы изменения отправились.

## Запрос изменений с сервера

Если вы сделали изменения в вашем удаленном репозитории, другие пользователи могут скачать изменения при помощи команды pull.

    $ git pull origin master
    From https://github.com/tutorialzine/awesome-project
    * branch master -> FETCH_HEAD
    Already up-to-date.

Так как новых коммитов с тех пор, как мы склонировали себе проект, не было, никаких изменений доступных для скачивания нет.

## Как удалить локальный репозиторий

Вам не понравился один из ваших локальных Git-репозиториев и вы хотите стереть его со своей машины. Для этого вам всего лишь надо удалить скрытую папку «.git» в корневом каталоге репозитория. Сделать это можно 3 способами:
 1. Проще всего вручную удалить эту папку «.git» в корневом каталоге «Git Local Warehouse».
2. Также удалить, не устраивающий вас, репозиторий можно на github. Открываете нужный вам объект и переходите в пункт меню Настройки. Там, прокрутив ползунок вниз, вы попадете в зону опасности, где один из пунктов будет называться «удаление этого хранилища».
3. Последний метод удаления локального хранилища через командную строку, для этого в терминале необходимо ввести следующую команду:

    
        cd repository-path/

        rm -r .git


[Следующая.](branch.md)