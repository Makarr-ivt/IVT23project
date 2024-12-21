Полезными операциями для производящих функций являются смещения начала.

Допустим, есть у нас функция $A(x)$, и мы хотим построить новую функцию $B(x)$, для которой ***коэффициенты $b_i$ смещены на $k$ элементов вправо от $a_i$***. При этом, чтобы сохранить нумерацию, первые $k$ элементов будут занулены. Можно записать $b_n$ следующим образом:
$$b_n = \cases{a_{n-k}, & $n \geq k$ \\ 0, & $0\leq n<k$}$$
Тогда, функцию $B(x)$ можно выразить через $A(x)$ следующим образом:
$$B(x) = x^kA(x)$$
И ведь действительно, первые элементы суммы зануляются, и степень $x^k$ можно вынести из под суммы по дистрибутивности:
$$\array{B(x) = \sum\limits_{n=0}^\infty b_nx^n = b_0 + b_1x + \ldots + b_{k-1}x^{k-1}+\sum\limits_{n=k}^\infty b_{n}x^n = \\ = 0 + \sum\limits_{n=0}^\infty b_{n+k}x^{n+k} = \sum\limits_{n=0}^\infty a_nx^{n+k} = x^{k}\sum\limits_{n=0}^\infty a_nx^n = x^kA(x)}$$
Или же по-другому:
$$\array{B(x) = \sum\limits_{n=0}^\infty b_nx^n = \sum\limits_{n=0}^\infty a_{n-k}x^{n} = \sum\limits_{n=k}^\infty a_{n-k}x^{n} = \\ = \sum\limits_{n=0}^\infty a_{n}x^{n+k} = x^k\sum\limits_{n=0}^\infty a_{n}x^{n} = x^k A(x)}$$
Альтернативно можно построить $B(x)$, для которой ***коэффициенты $b_i$ смещены на $k$ элементов влево от $a_i$***, хоть выглядит и немного страшнее:
$$b_{n} = a_{n+k} \Rightarrow B(x) = \frac{1}{x^k} \left(A(x) - \sum_{n=0}^{k-1}a_nx^n\right)$$
К счастью, она только *выглядит* страшно - в скобках мы из первоначальной функции вычитаем первые $k$ элементов - получится, будто первые $k$ элементов равны нулю, прямо как в примере до этого, когда мы смещали вправо - и в скобках получается $x^k B(x)$. Чтобы получить просто $B(x)$, соответственно нужно поделить на этот $x^k$, и получаем формулу выше.
$$\array{B(x) = \sum\limits_{n=0}^\infty b_nx^n = \sum\limits_{n=0}^\infty a_{n+k}x^n = \sum\limits_{n=k}^\infty a_{n}x^{n-k} = x^{-k}\sum\limits_{n=k}^\infty a_{n}x^{n} = \\ = x^{-k} \left(\sum\limits_{n=0}^\infty a_{n}x^{n} - \sum\limits_{n=0}^{k-1} a_{n}x^{n}\right) = \frac1{x^{k}}\left(A(x) - \sum\limits_{n=0}^{k-1} a_{n}x^{n}\right)}$$