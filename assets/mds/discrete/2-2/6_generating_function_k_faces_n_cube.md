Сначала определимся с понятиями.

$n$-мерное пространство - пространство с точками из $n$ координат. В трехмерном пространстве это три координаты $(x,y,z)$, в двухмерном - $(x,y)$, и т.д.

$k$-мерная грань - $k$-мерная фигура, которая составляет $n$-мерную фигуру. Так например для трехмерного куба, есть $8$ одномерных граней (вершин), $12$ двухмерных граней (отрезки между вершинами), $6$ трехмерных граней (грани в привычном понимании) и $1$ четырехмерная грань (куб).

Попробуем составить производящую функцию, где $a_k$ - количество $k$-граней у $n$-куба. Для этого перечислим случаи, которые мы можем посчитать в голове, и найдем закономерность: $a_0$ - вершины, $a_1$ - ребра, $a_2$ - грани, $a_3$ - кубы.
- $0$ пространств: $a_0 = 1$: $A(x) = 1$,
- $1$ пространство: $a_0 = 2$, $a_1 = 1$: $A(x) = 2 + 1x$,
- $2$ пространства: $a_0 = 4, a_1 = 4, a_2 = 1$: $A(x) = 4+4x+x^2=(2+x)^2$,
- $3$ пространства: $a_0 = 8$, $a_1 = 12$, $a_3 = 6$, $a_4 = 1$: $A(x) = 8 +12x+6x^2+x^3=(2+x)^3$.
- ...

В общем случае, получаем гипотезу $A(x) = (2+x)^n$ для $n$-мерного куба.
По индукции смотрим на $n > 3$:
$$A_{n+1}(x) = 2A_n(x) + xA_n(x) = A_n(x) \cdot (2+x) = (2+x)^{n+1}$$
Записывая производящую функцию как сумму, получаем:
$$(2+x)^n = \sum_{k=0}^\infty \binom n k 2^{n-k} x^k \Rightarrow a_k = \binom nk 2^{n-k}$$
Ответ: в $n$-мерном кубе $\binom nk 2^{n-k}$ $k$-мерных вершин.


## Бонус - составление без предположения
Это уже собственное решение, которое вероятнее всего не пригодится на экзамене.

Мы можем задать куб как фигуру из точек с координатами, принимающих только значения $0$ и $1$. Таким образом, у трехмерного куба есть восемь точек:
$$\array{(0,0,0) & (0,0,1) & (0,1,0) & (0,1,1) \\ (1,0,0) & (1,0,1) & (1,1,0) & (1,1,1)}$$
Аналогично, мы можем задать $k$-мерную грань нашего куба как фигуру из всех точек, где совпадают $n-k$ (одинаково позиционированных) координат. Тогда двухмерных граней (квадратов) у трехмерного куба будет шесть (звездочкой помечены свободные координаты грани):
$$\array{(1, \star, \star) & (\star, 1, \star) & (\star, \star, 1) \\ (0, \star, \star) & (\star, 0, \star) & (\star, \star, 0)}$$
Таким образом, количество $k$-мерных граней $n$-мерного куба находится комбинаторным образом: на упорядоченной паре из $n$ координат выбираем $n-k$ координат, на которых будем строить грани. Для каждой такой выборки существует $2^{n-k}$ возможных граней - выбор между $0$ и $1$ для каждой координаты. Таким образом, $k$-мерных граней $n$-мерного куба всего существует:
$$N_{k,n} = \binom n{n-k} \cdot 2^{n-k}$$
или же, т.к. $\binom n{n-k} = \binom nk$:
$$N_{k,n} = \binom nk \cdot 2^{n-k}$$
Подставляя в производящую функцию:
$$A(x) = \sum_{k=0}^\infty N_{k,n} x^n = \sum_{k=0}^\infty \binom nk \cdot 2^{n-k} \cdot x^n = (2+x)^n$$
Раскрывая эту скобку с помощью бинома Ньютона, для $n$-мерного куба число $k$-мерных граней будет стоять рядом со степенью $x^k$. Так, для трехмерного куба:
$$(2+x)^3 = 8+12x+6x^2+x^3$$
8 точек, 12 ребер, 6 сторон и 1 куб.

