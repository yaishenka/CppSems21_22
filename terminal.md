## Комманды для работы в терминале

- **man *[command]*** - посмотреть инструкцию по использованию команды ***[command]***. Можно листать вверх вниз стрелочками.

- стрелки вверх▲-вниз▼ - перемещаться по истории команд

- **whoami** - узнать свой username

- **pwd** - посмотреть, где мы находимся

- **date** - текущая дата и время

- **^C** - прервать работающую программу

- **^W** - стереть слово, **^U** - стереть всю строку 

  ###### Навигация

- **ls** или **ls .** - посмотреть содержимое *текущей* директории

- **ls *[dirname]*** - посмотреть содержимое указанной директории *[dirname]*

- **ls -l** - посмотреть содержимое в подробностях

- **ls -R** - посмотреть рекурсивно

- **ls -a** - посмотреть содержимое, включая скрытые файлы

  - **-l**, **-R** и **-a** - это опции команды **ls**. Их можно комбинировать:
    **ls -l -R -a** вернёт содержимое в подробностях для всех файлов (включая скрытые) во всех вложенных папках

- **cd *[dirname]*** - перейти в директорию

- **cd ..** - перейти вверх

- **cd -** - вернуться в предыдущую директорию

- **cd**, **cd ~** или **cd ~username** - перейти в домашнюю директорию

  ###### Создание файлов и директорий

- **mkdir *[dirname]*** - создать директорию ***[dirname]***

- **touch *[filename]*** - потрогать файл или создать пустой файл

  ###### Права доступа

- **chmod *[options]* *[filename]*** - поменять права доступа к файлу ***[filename]***

  - **+r**, **+w**, **+x** - добавить права на чтение, запись, исполнение
  - **-r**, **-w**, **-x** - забрать права на чтение, запись, исполнение

- **sudo *[command]*** - выполнить команду *[command]* от имени суперпользователя

  ###### Изменение файлов

- **cp *[from]* *[to]*** - скопировать файл

- **cp -r *[from]* *[to]***  - скопировать директорию

- **rm *[filename]*** - удалить файл

- **rm -r *[filename]*** - удалить директорию

- **rm -f *[filename]*** - принудительно удалить

- **mv *[from]* *[to]*** - переместить или переименовать (**-r** - переместить директорию)

  ###### Вывести файл в консоль

- **cat *[filename]***  - отобразить содержимое

- **head *[filename]*, tail *[filename]*** - отобразить первые или последние несколько строк
  ![img](http://acm.vdi.mipt.ru/twiki/pub/Cintro/WebHome/cat-head-tail-copy.jpg)

- **grep** - найти подстроку в файле

- **|** - перенаправить вывод первой команды во ввод второй 

- **rgrep** - рекурсивно найти подстроку в файлах директории

- **more** - отобразить содержимое с возможностью пролистывания

- **less** - отобразить с возможностью пролистывания вверх

  ###### Всякое разное

- **find . -name *[query]*** - найти файл

- **find . -name *[query]* -exec *[command]* {} +** - над всеми найденными файлами выполнить команду (**{}** - строка содержащая файлы найденные **find**'ом через пробел)

- **vim** - как зайти и как выйти, как вводить текст

  - Выйти: **ESC + :q! + Enter**

- **sudo apt-get install *[package]*** - как установить что-либо (python, clang)

  - Для маководов - **brew install *[package]***
  - На винде...
    [![Suicide cat Blank Template - Imgflip](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.imgflip.com%2F2lrers.jpg&f=1&nofb=1)](https://i.imgflip.com/2lrers.jpg)

- **python** - использование для простейших вычислений

- **gcc, g++ *[file.cpp]* -o *[output-file]*** - компиляция и запуск программ
  как копировать и вставлять текст в терминале