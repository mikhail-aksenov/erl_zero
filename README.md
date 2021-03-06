# erl_zero

Нулевая лабораторная работа для студентов. Знакомство с Erlang и работа над
простыми функциями.

## Материалы:

* http://erlang.org - сайт Erlang.
* https://try.github.io - набор упражнений по использованию git.
* http://www.tryerlang.org - набо упражнений по erlang.
* https://pragprog.com/book/jaerlang2/programming-erlang - основной учебник по
Erlang.

## Справка:

### Инсталляция Erlang:

Для того, чтобы можно было использовать Erlang для разработки приложений, 
необходимо сначала установить его на компьютер, используя либо готовые бинарные
установщики, либо собрав его из исходного кода.

* Установка на Windows

В зависимости от разрядности вашей операционной системы необходимо использовать
один из установщиков, которые размещены по ссылке http://www.erlang.org/download.html.

* Установка на MacOS X

Если в системе установлен менеджер приложений homebrew, то можно использовать
команду ``brew install erlang`` из терминала.

* Установка на Linux

В зависимости от дистрибутива необходимо воспользоваться либо пакетным менеджером,
установленным в системе, либо собрать Erlang из исходных кодов, которые размещены
по ссылке http://www.erlang.org/download.html.

### Типы данных Erlang:

Для того, чтобы немного поиграть с различными типами данных в Erlang, нужно запустить
его оболочку. Для Windows нужно запустить Erlang из меню "Пуск", для Linux или Mac OS X
shell можно запустить командой erl.

#### Числа:

Как и во многих других языках программирования в Erlang можно использовать целые и 
дробные числа в десятичной записи.

``` erlang

1> X = 1.
1
2> X + 2.
3
3> X * 3 + 5.
8
4> X1 = 5.0.
5.0
5> 1 + X1 * 2 / 4.0. % Стандартный приоритет арифметических операций.
3.5
6> 2#10. % Перед # можно указывать систему счисления для целых чисел.
2
7> 10#3.
3.
```

#### Атомы:

В Эрланге атомы являются аналогами констант. Вы уже использовали нечто похожее
, если знакомы с перечислениями из C или Java, и символами Ruby или Scheme.

С-программисты часто используют именованные константы для того, чтобы код было
проще читать. Типичная программа, написанная на C содержит файл, в котором
определено очень много различных констант, например файл glob.h:

``` c
#define OK 0
#define ARG_ERROR 1
#define OFL_ERROR 2
#define IO_ERROR 3
...
#define NOT_FOUND 235
...

```

В коде эти определения будут использоваться следующим образом:

``` c
  #include "glob.h"
  int result;
  result = read_file(buffer);
  if (result == OK) { }

```

Необходимо учитывать, что при таком использовании констант их числовые значения
не важны. Они используются только для того, чтобы сравнить код возврата на 
равенство (достаточно бессмысленно складывать коды ошибок друг с другом).

Эквивалентная программа на Эрланге выглядела бы следующим образом:

``` erlang
  Result = read_file(buffer).
  if 
    Result == ok ->
      ...

```

Атомы в Эрланге глобальны и не зависят от макроописаний. Атомы объявляются как
идентификаторы, начинающиеся со строчной буквы латинского алфавита и могут
содержать числа, латинские буквы, знак подчеркивания, коммерческое at (@).
Например, monday, red, cat, long_atom_value, some_data@company.

Также атомы можно заключить в одинарные кавычки (''). В этом случае, атомы могут
начинаться и с заглавной буквы или содержать пробемы, например, 'Monday'.
Необходимо отметить, что атомы, заключенные в кавычки, но написанные без
дополнительных символов эквивалентны, т.е. `a == 'a'`.

#### Строки:



#### Битовые строки:

#### Кортежи:

#### Списки:

#### Хэш-таблицы:

### Модули:

В Эрланге пространство имен называется модулем. Обычно, каждый модуль - это один
файл с расширением .erl, который в заголовке содержит следующую информацию:

``` erlang

-module(name). % Директива, указывающая имя модуля. 
% name всегда совпадает с именем файла.
-export([fn1/1, fn2/3, fn3/5...]). % Список экспортируемых функций.
% Для каждой функции указывается ее имя и количество аргументов.
% Если функция экспортирована, то может быть вызвана из другого модуля 
% следующим образом:
% name:fn1(x).

fact(X) ->
  if X > 1 then
    X * fact(X - 1)
  else
    1
  end.

```

### Типовая структура проекта:

http://www.erlang.org/doc/design_principles/applications.html#7.4

- ebin - содержит скомпилированные .beam файлы. Также в эту директорию помещается файл описания приложения (.app).
- include - содержит зависимые модули для приложения.
- priv - содержит файлы, специфичные для приложения, например исполняемые программы, написанные на C. Для доступа к этой директории необходимо использовать функцию code:priv_dir/1.
- src - содержит исходные коды приложения.


## Задание:

1. Разработать функцию, вычисляющую факториал числа.
2. Разработать функцию, вычисляющую число Фибоначчи с заданным номером.
3. Разработать функцию, обращающую список.

### Разработка:

