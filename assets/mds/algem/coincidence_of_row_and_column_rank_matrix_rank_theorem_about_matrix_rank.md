Строчный ранг матрицы определяется как максимальное количество линейно независимых строк в этой матрице. То есть, если в матрице есть линейно независимая система из $r_1$ строк и нет линейно независимой системы из большего количества строк, то строчный ранг этой матрицы равен $r_1$. Строчный ранг матрицы $A$ обозначается как $r_1(A)$.
Для определения строчного ранга нужно найти количество строк, которые не могут быть выражены как линейные комбинации других строк.
В частности, нулевая матрица имеет ранг, равный нулю, ведь нулевые векторы являются линейно зависимыми даже по одиночке.

Соответствующее определение есть и для столбцового ранга, $r_2(A)$.
Так же отметим, что определения ранга не зависит от квадратности матрицы - ранг определен для матриц любого размера.

Если назвать все строки, входящие в ту самую линейно независимую систему, *базисными*, то можно утверждать, что любая строка раскладывается как линейная комбинация базисных векторов - это следует из свойств линейно независимой системы векторов. Если мы говорим про разложение базисных строк, то можно занулить все строки, кроме той самой базисной строки, которую мы раскладываем. Если же мы раскладываем какую-то другую строку, то при присоединении ее к базисным, система становится линейно зависимой, а значит эту строку возможно разложить как линейную комбинацию базисных.

На основе теоремы про элементарные преобразования, и что они не меняют характер вырожденности матрицы, можно утверждать, что ранг матрицы $A$ так же не меняется при элементарных преобразованиях.
Если из матрицы убрать строчку, то строчный ранг матрицы не может увеличиться, ведь линейно зависимых строк явно больше не становится. Соответствующее свойство есть и для столбцового ранга (удивительно).
## Эти ранги равны?
Докажем две вспомогательные простенькие леммы перед этим.
1. Любой столбик высоты, равной высоте невырожденной матрицы, можно разложить по ее столбикам, причем единственным образом.
   Вытекает свойство естественно из свойств линейно независимых систем. Если матрица $A$ - невырождена, можно взять ей обратную. Выразим произвольный столбик $b$: $$b = AA^{-1}b = A(A^{-1}b)$$
   Получается, с помощью умножения столбка $A^{-1}b$ на матрицу $A$ возможно получить столбик $b$.
2. Любые $n+1$ строк длиной $n$ линейно зависимы: если строки изначально были линейно зависимы, все очев. Если же нет, эти строки составляют невырожденную матрицу $n \cross n$ - по прошлой лемме доказывается это утверждение.

Я утверждаю, что столбцовый и строчный ранг всегда равны.
Для этого для произвольной матрицы $n \cross m$ найдем ее ранги, $r_1(A)$ и $r_2(A)$. Выделим матрицу $D$, которая находится на пересечении базисных строк и столбцов - она будет размеров $r_1(A) \cross r_2(A)$.

Для такой матрицы не может быть, чтобы $r_1(A) > r_2(A)$, ведь это бы значило, что линейно зависимых строк в матрице больше, чем всего есть столбиков, что как мы сказали (лемма 2), не бывает. То есть, как минимум, $r_1(A) \geq r_2(A)$. Соответствующие рассуждения действуют и для транспонированной матрицы $A^T$: поэтому $r_1(A^T) \geq r_2(A^T)$.
Но ведь при транспонировании матрицы все строчки и столбики меняются, отчего естественно свойство $r_1(A^T) = r_2(A)$, как и $r_2(A^T) = r_1(A)$.
Получается, $r_2(A) \geq r_1(A)$. Но единственный случай, когда оба таких неравенства могут быть удовлетворены: $$r_1(A) = r_2(A)$$
Поэтому столбцовый и строчный ранги равны, и обозначается общий ранг матрицы как $\rg A$.
Раз "столбцовый и строчный" ранги равны, будут равен и "строчный и столбцовый" ранги: при транспонировании ранг не меняется. $$\rg A = r_1(A) = r_2(A^T) = \rg A^T$$
## Смысл за рангом
Геометрически, ранг представляет собой количество измерений нового пространства, в которые матрица преобразовывает старое пространство. Например, если после применения матрицы $3 \cross 3$ все вектора стали лежать на некоторой плоскости, то ее ранг будет равен $2$. Стали бы они лежать на прямой - ранг был бы равен $1$.
Это так же причина, почему ранг нулевой матрицы равен нулю - все вектора сожмутся в одну точку, в ноль пространства.
Самый простой пример матрицы с рангом $2$ - матрица $3 \cross 3$, проектирующая все векторы на ось $Oxy$ - ее $z$ столбик занулен, поэтому и получается проекция:
$$\pmatrix{1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0}$$
## Теорема о ранге матрицы
Теорема звучит так: строчный и столбцовый ранги матрицы равны, и равны порядку базисной подматрицы.
Базисная подматрица - это матрица, образованная базисными строками и столбцами, элементами на их пересечении. Раз строчный ранг равен столбцовому, как мы доказали в прошлом билете, эта матрица будет квадратная, порядка $\rg A$. Базисная подматрица будет невырожденная, ведь образована из базисных строк.

В матрице ранга $r$ не может быть подматрицы с рангом выше $r$. Если бы такая матрица существовала, она бы по определению ранга (ранг - максимальное количество линейно независимых векторов) состояла бы из линейно зависимых строк, и была бы вырожденной как следствие.

Заметим, что базисная матрица может существовать не одна: самый простой пример в матрице $$A = \pmatrix{1 & 0 \\ 2 & 0}$$
Тут матрица вырождена, и ранг ее равен $1$, однако существуют базисные матрицы как $(1)$, так и $(2)$.