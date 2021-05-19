# ft_printf
## Структура ft_printf

*ft_printf* получает строку, называемую форматом, которая может содержать ряд заполнителей представленных после символа % и тип преобразования данных (строка (str), символ (char), int в десятичное, int в шестнадцатеричное и т. д.) Синтаксис: 
```
%[flags][width][.precision][length]type
```

Краткое изложение различных типов:

|   Тип формата   |   Тип аргумента   |   Результат   |
|:----------:|:----------------:|:------:|
|      d / i |   int  | Печатает int в десятичной форме |
|   u   |   unsigned int   | Печатает unsigned int в десятичной форме |
|   x   |   unsigned int   | Печатает int в шестнадцатеричной форме (в нижнем регистре)  |
|   X   |   unsigned int   | Печатает int в шестнадцатеричной форме (в верхнем регистре) |
|   c   |   char   | Печатает символ |
|   s   |   char *   | Печатает строку |
|   p   |   void *   | Печатает адрес указателя |

Между «%» и типом преобразования может находиться ряд параметров: ширина (число или *), модификаторы длинны (h, hh, l, ll, L), точность (число или *), флаги (#, 0, ' ', +, -).

*Ширина поля* - это минимальная длина строки, полученная в результате преобразования, и указывается в виде числа. По умолчанию, если пpеобpазованное значение имеет меньшее количество знаков, чем шиpина поля, то оно слева дополняется пpобелами (или спpава, если указан флаг левого пpеобpазования). заполнения дополнительных символов слева. Небольшая ширина не делает результат преобразования усеченным - если pезультат пpеобpазования больше шиpины поля, то поле pасшиpяется, чтобы вместить в себя пpеобpазованное значение.

*Точность* - это десятичное число, перед которым стоит точка. Для типов diuxX точность - это минимальная длина строки, дополненная слева 0, если результат преобразования короче, чем точность. Для преобразования f точность указывает количество цифр до которых необходимо округлить число. Для преобразований s точность дает максимальное количество символов, которые должны быть напечатано из аргумента.

| Flag | Effect |
|:----:|:------:|
| - | Выровнять по левому краю в пределах ширины поля |
| + | Принудительно ставит знак "+" перед положительными числами |
| ' ' (пробел) | Перед значением вставляется пробел, если нет знакак перед числом |
| 0 | Поле заполняется нулями вместо пробелов по умолчанию |


## Как пользоваться?

Командой make компилируем ft_printf и создаём библиотеку libftprintf.a, которую можно будет использовать в дальнейших проектах. 
