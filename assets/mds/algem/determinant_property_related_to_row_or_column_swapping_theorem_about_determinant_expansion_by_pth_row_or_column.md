## Перестановка строк/столбцов
Свойство таково - если поменять любые две строки (или столбца) в матрице, то ее определитель изменит знак. Другими словами, поменяется ориентация базиса.

Доказательство начинается с доказательства этого свойства для двух соседних строк, а затем будет расширение этого свойства для двух любых строк.
1. Как всегда, по индукции начинаем рассуждать. Вводим базу $n=2$, и ручками доказываем: $$\left|\array{a&b\\ c&d}\right| = ad-bc = -(cb-da) = -\left|\array{c&d\\ a&b}\right|$$
   Полагаем, что формула работает для матриц порядка $n-1$, и докажем что тогда формула работает и для матриц порядка $n$.
   Теперь рассматриваем два соседних элемента, допустим строки $p$ и $p+1$. Пусть матрица $A$ и $B$ совпадают, за исключением элементов на строках $p$ и $p+1$, которые были поменяны. $$\cases{a_{pi} = b_{(p+1)i} \\ a_{(p+1)i} = b_{pi}}, \ \ \ \ \ i \in \overline{1, n}$$
   Запишем разложения определителей этих двух матриц по первому столбцу: $$\array{|A| = \sum_{i=1}^n (-1)^{i+1} a_{i1} \cdot \det \bar A^i_1 \\ |B| = \sum_{i=1}^n (-1)^{i+1} b_{i1} \cdot \det \bar B^i_1}$$
   Теперь выделим из этих сумм члены $p$ и $p+1$ (не пугайтесь суммы на следующей строке, они просто не вмещаются на одну линию): $$|A| = (-1)^{p+1}a_{p1}\det \bar A^p_1+ (-1)^{(p+1)+1}a_{(p+1)1}\det \bar A^{p+1}_1 +$$$$+ \sum_{i=1, i\neq p, i\neq p+1}^n (-1)^{i+1} a_{i1}\det \bar A^i_1$$$$|B| = (-1)^{p+1}b_{p1}\det \bar B^p_1+ (-1)^{(p+1)+1}b_{(p+1)1}\det \bar B^{p+1}_1 +$$$$+ \sum_{i=1, i\neq p, i\neq p+1}^n (-1)^{i+1} b_{i1}\det \bar B^i_1$$
   В суммах мы просто искусственно убрали из суммы итерацию по строкам $p$ и $p+1$.
   Теперь преобразуем члены в определителе $|B|$:
   - По определению матрицы $B$, $b_{p1} = a_{(p+1)1}, b_{(p+1)1} = a_{p1}$.
   - По индукционному предположению, $\det \bar B^i_1 = -\det A^i_1$: $$|B| = (-1)^{p+1}a_{(p+1)1}\det \bar B^p_1+ (-1)^{(p+1)+1}a_{p1}\det \bar B^{p+1}_1 -$$$$- \sum_{i=1, i\neq p, i\neq p+1}^n (-1)^{i+1} b_{i1}\det \bar A^i_1$$
   - Миноры в выделенных членах на самом деле не изменились по строкам, и поэтому $\det \bar B^p_1 = \det \bar A^{p+1}_1$ и $\det \bar B^{p+1}_1 = \det \bar A^{p}_1$.![[algem-39-1.png]]
   - Несмотря на то, что сами миноры не изменились, они находятся под разными знаками в силу $(-1)^{p+1}$ и $(-1)^{p+2}$ - поэтому эти определители будут стоять под противоположным знаком по сравнению с теми, что стоят в определителе $|A|$: $$\array{|B| = (-1)^{p+1}a_{(p+1)1}\det \bar A^{p+1}_1+ (-1)^{(p+1)+1}a_{p1}\det \bar A^{p}_1 - \sum \ldots= \\ = - (-1)^{p+1}a_{p1}\det \bar A^{p}_1 - (-1)^{(p+1)+1}a_{(p+1)1}\det \bar A^{p+1}_1 - \sum \ldots = \\ = -|A|}$$
Вот такими алгебраическими преобразовании мы и показали, что при перестановке двух соседних строк определитель обязательно изменит свой знак.
Расширим наше свойство для произвольных строк. Поменяем две строки с номерами $p$ и $p+q$. Посчитаем, сколько нужно обменов соседних строк, чтобы поменять лишь эти две строчки:
1. Сначала мы двигаем строку $p$ в сторону $q$. Мы начинаем обмен $(p, p+1)$, затем $(p+1, p+2)$, и так далее, последним обменом станет $(p+q-1, p+q)$. В этот момент строка, что раньше была на позиции $p$, станет на позицию $p+q$, а строка $p+q$ сместится на позицию $p+q-1$. Итого всего произошло $q$ обменов. ![[algem-39-2.png]]
2. Теперь осталось подвинуть строчку $p+q$ (которая теперь уже на $p+q-1$) на позицию $p$. Для этого мы точно так же обмениваем строчки, но в обратном порядке: $(p+q-1, p+q-2)$, $(p+q-2, p+q-3)$, и в конце будет $(p+1, p)$. Итого $q-1$ обмен. Можно представить по-другому: обмен $p\rightarrow q$ и $q \rightarrow p$ симметричен, но когда мы обмениваем в одну сторону, вторая строчка смещается на 1 ближе к цели, поэтому в итоге будет на одно меньше действие.![[algem-39-3.png]]
Сколько всего получилось обменов? $q + q-1 = 2q-1$, а это нечетное число. Значит, какую бы строчку мы не меняли, всегда произойдет нечетное количество обменов, а значит нечетное количество раз перевернется знак - а значит, он всегда после таких обменов изменится на противоположный. Вот такое интересное доказательство.

Для столбиков доказательство аналогичное, хотя можно и продолжить сразу из рабочего доказательства для строчек и применения теореме о определителе транспонированной матрицы. Если $B$ мы получили с помощью перестановки двух столбцов из матрицы $A$, то $B^T$ будет получена путем перестановки двух строк из матрицы $B^T$. А как мы знаем, определители матрицы и ее транспонированной равны, посему:
$$\det A = \det A^T = -\det B^T = -\det B$$

Из этого свойства становится видно, почему смешанное произведение кососимметрично - меняет свой знак при обмене двух векторов местами. Смешанное произведение ведь считается как определитель третьего порядка, а как мы показали, при обмене строк меняется знак - отсюда и свойство.

Еще одно забавное следствие из этого свойства - если два столбика/строчки равны друг другу, то определитель матрицы равен нулю. С одной стороны, когда мы их поменяем местами, знак должен измениться. С другой стороны, матрица не изменилась (ведь строчки равны друг другу), поэтому и определитель тоже не должен был измениться. Эти два факта приводят лишь к тому, что определитель равен нулю.
## Определитель по любой строке/столбцу
Раньше мы брали определитель по первой строке/столбцу. Так же мы знаем, что при смещении соседних строк определитель меняет знак. Из этого вытекает, что сместив $p$-тую строку/стобцев на первое место и поменяв знак по четности $p$, возможно взять определитель по $p$-той строке/столбцу. Получаются следующие формулы разложения по $p$-той строке или столбцу:
$$\det A = \sum_{i=1}^n (-1)^{p+i} a_{ip} \bar M^i_p$$
$$\det A = \sum_{j=1}^n (-1)^{j+p} a_{pj} \bar M^p_j$$
Доказательство выглядит не сложно: перемещаем $p$-тую строку матрицы $A$ перестановками соседних строк, чтобы $p$-тая строка стала первой. На это потребуется $p-1$ перестановок, и соответственно у получившейся матрицы $B$, определитель $\det B = (-1)^{p-1} \det A$.
Соответственно раскладываем определитель матрицы $B$ по первой строке, и заменяем переменные на элементы матрицы $A$:
$$\det B = \sum_{j=1}^n (-1)^{j+1} b_{1j}\det \bar B^1_j$$
Элементы $b_{1j}$, из-за того что мы переставляли строки из матрицы $A$, будут равны элементами $a_{pj}$. Дополнительный минор $\det \bar B^1_j$ будет соответствовать минору $\det \bar A^p_j$ по той же причине. ![[algem-39-4.png]]
Переписываем:
$$\det B = \sum_{j=1}^n (-1)^{j+1} a_{pj} \det \bar A^p_j$$
В свою очередь, $\det B = (-1)^{p-1} \det A$, из-за чего кстати следует и обратное утверждение: $\det A = (-1)^{p-1} \det B$ (просто поделили на $(-1)^{p-1}$). Подставляем и считаем:
$$\det A = (-1)^{p-1} \det B = \det A = (-1)^{p-1} \sum_{j=1}^n (-1)^{j+1} a_{pj} \det \bar A^p_j$$
$$\det A = \sum_{j=1}^n (-1)^{j+p} a_{pj} \det \bar A^p_j$$
Что и доказывает работоспособность этой формулы. Доказательство для столбиков аналогично.
В силу этого свойства вытекает, что если в матрице есть нулевая строка/столбик, то определитель этой матрицы равен нулю - достаточно просто разложить определитель по этой строке/столбцу, чтобы это заметить.

Из этого свойства следует, что "матрица знаков" на матрице расположена в шахматном порядке. На "белых клетках" стоит плюс, на "черных" - минус. При разложении по любой строке/столбцу достаточно умноажть элементы на миноры в соответствии с этими знаками:
![[algem-39-5.png]]
## Пример задачи
Условие: посчитайте определитель матрицы $A$ по второй строке $$A = \begin{pmatrix}9 & 3 & -1 \\ 6 & -5 & 1 \\ 8 & 2 & 6\end{pmatrix}$$

Решение: вторая строка - четная, поэтому начинаем чередовать с минуса. $$\array{|A| = -6\left|\matrix{3 & -1 \\ 2 & 6}\right| + (-5)\left|\matrix{9 & -1 \\ 8 & 6}\right| - 1\left|\matrix{9  & 3 \\ 8 & 2}\right| = \\ = -6(18+2) - 5(54+8) - 1(18-24) = -424}$$

---
Условие: посчитайте опредитель матрицы $B$ по третьему столбцу $$B = \begin{pmatrix}2 & 6 & 1 \\ 3 & 7 & -2 \\ 9 & 8 & -4\end{pmatrix}$$

Решение: третий столбик - четный, поэтому начинаем чередовать с плюса.
$$\array{|B| = 1\left|\matrix{3 & 7 \\ 9 & 8}\right| - (-2)\left|\matrix{2 & 6 \\ 9 & 8}\right| + (-4)\left|\matrix{2 & 6 \\ 3 & 7}\right| = \\ = 1(24 - 63) + 2(16 - 54) - 4(14-18) = -99}$$