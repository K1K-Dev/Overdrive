# Документация
* [Переменные](#Переменные)
* [Вывод в консоль. Первая прграмма](#Вывод-в-консоль)
* [Консольный ввод](#Консольный-ввод)
* [Условные конструкции](#Условные-конструкции)
* [Циклы](#Циклы)
* [Функции](#Функции)
* [Return в функциях](#Return-в-функциях)
* [Библиотеки](#Библиотеки)

# Переменные
Для обьявления переменных есть секция Data

Существуют переменные двух типов `int` и `string`
```python
Data():
    string a;
    int b;
```


# Вывод в консоль
Весь код выполняется в секции `Start()`
Для вывода в консоль есть 2 функции `Print` и `std:PrintF`
```python
Data():
    string a = "Hello_World!";
Start():
    Print: a;
```
Для использования `std:PrintF` нужно импортировать библиотеку `std`
```python
#include "std.ovdh"
Data():
    string a = "Hello_World!";
Start():
    std:PrintF: a;
```

# Консольный ввод
Для ввода в консоль есть функция `Input`
```python
#include "std.ovdh"
Data():
    string a = "Hello_World!";
Start():
    Input: a;
    std:PrintF: a;
```
Во избежание ошибок для вывода в консоль измененного текста нужно использовать `std:PrintF`

# Условные конструкции
Условие состоит из `if` и `else`
```python
if b == c:
    Print: a;
endif;
```
С исспользованием `else`
```python
if b == c:
    Print: a;
else:
    Print: L;
endif;
```
* `if` - если
* `else` - иначе

Операторы сравнения:

* `==` - равно
* `!=` - не равно
* `>` - больше
* `<` - меньше

# Циклы
Пример цикла `While`
```python
While 10:
    Print: a;
End_While;
```
В данном примере переменная `a` будет выведенна в консоль 10 раз

Пример цикла `For`
```python
Data():
    string a = "Hello_World!";
int b = 0;
int c = 10;
Start():
    For b < c +:
        Print: a;
    End_While;
```
В данном примере переменная `a` будет выведенна в консоль 10 раз, и к переменной `b` будет прибавленно 10

# Функции
Для определения функции используется ключевое слово `Function`, далее идет название функции
```python
Function Z:
    Print: a;
End_Function;
```
Для вызова функции используется ключевое слово `Call_Function`, далее идет название функции
```python
Call_Function: Z;
```
# Return в функциях
Для того чтобы задать значение функции используется ключевое слово `return`, вместо `End_Fuction`
```python
Function Z:
    Print: a;
    b = 10;
return b;
```
В данном примере переменная `b` это результат функции
Для того чтобы получить значение из функции нужно вызвать функцию и использовать используется ключевое слово `Function_Return`
```python
Call_Function: Z;
Function_Return d;
```
В данном примере переменная `d` будет равна результату функции Z

# Библиотеки 
Все библиотеки должны храниться в папке `Libs`, и иметь расширение `.ovdh`. Допустим библиотека будет называться V.ovdh

Пример библиотеки:
```python
string a = "Hello_World";
Function Z:
    Print: a;
End_Function;
```
* В библиотеках не используются секции `Start()` и `Data()`

Пример использования библиотеки:
```python
#include "V.ovdh"
Data():

Start():
    Call_Function: Z;
```
* Для импорта библиотек используется ключевое слово `#include`
