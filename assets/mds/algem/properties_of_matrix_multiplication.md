Билет [#34. Умножение матриц.](?algem/34) очевидно важен для этого, но я так же рекомендую так же прочитать и раздел со *смыслом* умножения, ведь множество свойств натурально вытекают из того, что матрицы описывают трансформации пространства.

- Умножение матриц НЕ КОММУТАТИВНО!!! $$A \cdot B \neq \neq \neq B  \cdot A$$
  Во-первых, можете представить себе случайные две матрицы, и перемножить их - шансы велики, что результаты будут разные. Если говорить о матрицах как о трансформациях, то видно, что "сначала поворот, потом растяжение" и "сначала растяжение, потом поворот" - разные трансформации.
  Однако то, что умножение не коммутативно, не значит, что не существует таких матриц, что $AB = BA$. Матрицы, которые удовлетворяют равенству $AB=BA$ называют *коммутирующими между собой*.
  Если $A$ - единичная матрица, то равенство выполняется для любой матрицы $B$. Матрица $A$ в данном случае представляет собой "пустую трансформацию" - она никак не сдвигает базисные вектора с позиции, в которой они стоят, поэтому применим мы пустоту "до" или "после" не изменит исход матрицы $B$. Из этого следует, что *единичная матрица коммутирует с любой матрицей*.
- Умножение матриц ассоциативно: $$(AB)C = A(BC)$$
  На языке трансформаций ясно, что "применить трансформацию $C$, потом применить трансформацию $B$ и $A$" и "применить трансформацию $C$ и $B$, потом применить трансформацию $A$" - одинаковые операции (единственное что изменилось, быть может - интонация).
  Алгебраическое доказательство просто показывает равенство сумм: Элементы матрицы $AB$ считаются по следующей формуле $$(AB)_{ij} = \sum_k A_{ik}B_{kj}$$
  Соответственно произведение $(AB)C$ будет выглядеть так: $$((AB)C)_{xy} = \sum_l \left(\sum_k A_{xk}B_{kl}\right)C_{ly}$$
  С другой стороны, элементы матрицы $BC$: $$(BC)_{ij} = \sum_k B_{ik}C_{kj}$$
  И произведение $A(BC)$ будет выглядеть как $$(A(BC))_{xy} = \sum_l A_{xl}\left(\sum_k B_{lk}C_{ky}\right)$$
  Эти два выражения равны - суммируются одни и те же числа, просто в разном порядке. Доказательство окончено.
- Умножение матриц дистрибутивно к сложению: $$(A+B)C = AC + BC \ \ \ \ \ \ \ A(B+C) = AB + AC$$
  Это свойство вытекает из дистрибутивности умножения и сложения обычных чисел. Разберем левое выражение: элемент произведения слева равен $$((A+B)C)_{ij} = \sum_k (A_{ik} + B_{ik})C_{kj}$$
  А справа: $$(AC + BC)_{ij} = (AC)_{ij} + (BC)_{ij} = \sum_k A_{ik}C_{kj} + \sum_k B_{ik}C_{kj}$$
  Но сумма дистрибутивна, отчего видно, что верхнее и нижнее выражения равны.
- Ассоциативность по отношению к умножению на скаляр: $$\alpha(AB) = (\alpha A)B = A(\alpha B)$$
  Как и предыдущее свойство, следует напрямую из свойств обычного умножения чисел.

- Интересное свойство возникает с транспонированием. Транспонирование произведения матриц - то же самое, что и произведение транспонированных матриц в обратном порядке. $$(AB)^T = B^TA^T$$
  Доказательство алгебраическое, но несложное. Представим произведение $AB$: $$(AB)_{ij} = \sum_k A_{ik}B_{kj}$$
  Соответственно для транспонированной матрицы:$$(AB)^T_{ij} = (AB)_{ji} = \sum_k A_{jk}B_{ki}$$
  А для произведения $B^TA^T$:$$(B^TA^T)_{ij} = \sum_k B^T_{ik}A^T_{kj} = \sum_k B_{ki}A_{jk}$$
  Как видно, получились одинаковые элементы, что и завершает это доказательство.
  Это свойство, кстати, можно расширить до сколь угодно количества матриц: $$\array{(ABC)^T = (BC)^TA^T = C^TB^TA^T \\ (ABCD)^T = D^T(ABC)^T = D^TC^T(AB)^T = D^TC^TB^TA^T}$$
  