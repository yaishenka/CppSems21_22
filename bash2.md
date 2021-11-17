# Работа в терминале - часть 2

## touch

### Создание пустых файлов

С помощью команды touch можно создать пустой файл:

```bash
touch test.cpp
```

Также можно создать несколько файлов

```bash
touch test1 test2 test3 test4
```

Эта команда, кстати аналогична следующей

```bash
touch test{1,2,3,4}
```

### Копирование временной метки

```bash
touch test
touch -r test new
```

### Изменение метки времени последнего доступа к файлу

Проверить эту метку можно так:

```bash
ls -l test --time=atime
```

Изменить так:

```bash
touch -a test
```

### Изменение метки времени последнего изменения файла

```bash
touch -m test
```

(посмотреть ее можно так: ls -l test)

### Изменение даты

```bash
touch -d '15 Mar' test
```

еще можно так

```bash
touch --date="yesterday" test
```

### Изменение времени

```bash
touch -t 2025 02 01 04 22 test
```

## ln

Команда ln позволяет создавать жесткие и символические ссылки

[подробнее](https://losst.ru/simvolicheskie-i-zhestkie-ssylki-linux)

### Символические ссылки

По сути просто ярлык, если исходный файл удалить, то ссылка будет невалидная:

```bash
ln -s source dest
```

### Жесткие ссылки

Указывает на кусок жесткого диска. Ведет себя как файл

```bash
ln -P source dest
```

## tar 

Встроенный архиватор

[подробнее](https://losst.ru/komanda-tar-v-linux)

Синтаксис:

```bash
tar опции архив файлы (для сжатия)

tar опции архив (для архивации)
```

### Создание архива

Можно, например, вот так

```bash
tar --totals --create --verbose --file archive.tar file1 file2 file3
```

### Просмотр содержимого

```bash
tar -tf archive.tar
```

### Распаковка архива

```bash
tar -C "dest" -xvf archive.tar
```

### Сжатие файлов

Можно сжимать либо с помощью bzip2 либо с помощью gzip. Флаги -j -z соответственно

## grep (global regular expression print)

[подробнее](https://losst.ru/gerp-poisk-vnutri-fajlov-v-linux)

Варианта по сути два

```bash

command | grep опции шаблон

grep опции шаблон имя_файла
```

### grep -r

Запускает рекурсивный поиск по каталогу и его подкаталогам

### (Задачка) найти все строки в файлах, начинающиеся/заканчивающиеся на данное слово

<details>
  <summary>Слово в начале</summary>
  ```bash
  grep -rw "^word" source/
  ```
</details>

<details>
  <summary>Слово в конце</summary>
  ```bash
  grep -rw "word$" source/
  ```
</details>

### Или в regexp

```bash
grep "word|test"
```

### (Задачка) в скольких строках файла данное слово встречается хотя бы дважды

<details>
  <summary>Решение</summary>
  ```bash
  grep "word.*word" -c test.txt
  ```
</details>

## sed

sed - потоковый редактор текста 

[подробнее](https://losst.ru/komanda-sed-linux)

### Вывод строк файла с n по m

```bash
sed -n '5,10p' test.txt
```

### Вывод строк файла кроме n-m

```bash
sed '1,20d' test.txt
```

### Замена слов

```bash
sed 's/word/test/g' test.txt
```

## cut

Позволяет вырезать данные из файла

[подробнее](https://losst.ru/komanda-cut-linux)

## sort

Позволяет сортировать строки

[подробнее](https://losst.ru/komanda-sort-v-linux)

## uniq

[подробнее](https://losst.ru/komanda-uniq-linux)

## xargs

[подробнее](https://losst.ru/komanda-xargs-linux)

## > и 2>

> перенаправляет stdout 

2> перенаправляет cerr

## >>

тоже самое, что и >>, только дописывает в файл а не перезаписывает

## /dev/null

"Мусорка", куда можно отправлять ненужный вывод

## tee

[подробнее](https://losst.ru/komanda-tee-linux)

Позволяет записывать в несколько файлов






