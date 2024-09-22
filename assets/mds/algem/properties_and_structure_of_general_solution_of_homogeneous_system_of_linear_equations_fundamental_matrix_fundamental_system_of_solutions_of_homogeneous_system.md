## Однородные системы
Рассмотрим *однородную* систему - когда столбик $b$ равен нулю:
$$Ax = 0$$
Такая система всегда будет совместна, потому что как минимум существует тривиальное решение ($x_i = 0$). Существование других решений зависит от ранга матрицы $A$.
По отношению к системе $Ax = b$ такая система называется *приведенной*, ведь в этой системе $b = 0$.

Приведенные системы и оригинальные связаны своими решениями: пусть существует решение оригинальной системы $x_0$. Если $y$ - решение приведенной системы, то $x = x_0 + y$ тоже будет решением оригинальной системы. Покажем это:
Пусть $y$ - решение приведенной системы. Тогда, по линейности матриц:
$$Ax = Ax_0 + Ay = b + 0 = b$$
И обратно, если $x$ - решение оригинальной системы, то $y = x-x_0$:
$$Ay = Ax - Ax_0 = b - b = 0$$
Более того - если $x_1$ и $x_2$ - решения приведенной системы, то любая их линейная комбинация также будет решением приведенной системы:
$$Ax_1 = 0, Ax_2 = 0 \Rightarrow A(\alpha x_1 + \beta x_2) = Ax_1\alpha + Ax_2\beta = 0\alpha+0\beta=0$$
Таким образом, мы можем описать множество решений совместной системы через множество решений приведенной системы. Нам достаточно решить приведенную систему и найти лишь одно решение оригинальной - этого достаточно, чтобы описать *все* решения оригинальной.
## Фундаментальная система решений и фундаментальная матрица
Эта мысль натурально подводит нас к идее *фундаментальной системе решений* (ФСР): мы можем указать все (линейно независимые) решения приведенной системы и записать их в одну матрицу. Матрица $F$ высотой $n$ будет называться *фундаментальной матрицей* для однородной системы с матрицей $A$ размеров $m \cross n$, если:
1. $AF = 0$ (каждый столбик матрицы $F$ является линейной комбинацией для любой строки $A$, который обнуляет ее - решение приведенной системы).
2. Столбики $F$ линейно независимы.
3. Каждое решение уравнения $Ax=0$ раскладывается по столбцам матрицы $F$.

Столбики фундаментальной матрицы и называются *фундаментальной системой решений (ФСР)*.
Таким образом, любая линейная комбинация столбиков ФСР будет являться решением приведенной системы. Если $f_i$ - $i$-тый столбик матрицы ФСР, то общий вид решения системы выглядит так:
$$x = \alpha_1 f_1 + \alpha_2 f_2 + \ldots + \alpha_3 f_3$$
Если приведенная система не имеет нетривиальных решений, то второе условие - линейная независимость столбиков - не может быть выполнено (ведь нулевой столбик является тривиальным решением и уже сразу линейно зависим), и фундаментальной матрицы быть не может.
Заметьте, что ничего не обязывает фундаментальную матрица $F$ быть квадратной!

Теперь поговорим про ее свойства:
Любая линейная комбинация столбцов $F$ является решением приведенной системы. Более формально:
Пусть фундаментальная матрица $F$ состоит из $p$ столбцов. Тогда, $x$ является решением уравнения $Ax = 0$ тогда и только тогда $(\Leftrightarrow)$, когда найдется столбец $c$ высоты $p$, что $x = Fc$ - линейная комбинация столбцов матрицы $F$.

Если $x$ является решением уравнения, из третьего условия на матрицу $F$ следует существование столбца $c$. В другую сторону, существование $c$ влечет за собой существование решения уравнения $x$ из-за ассоциативности умножения и первого условия:
$$Ax = A(Fc) = (AF)c = 0c = 0$$