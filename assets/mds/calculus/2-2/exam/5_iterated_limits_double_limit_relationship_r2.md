Пусть дана функция $f(x,y)$. Рассмотрим функцию для каждого значения $x$ как предел по $y$:
$$\varphi(x) = \lim_{y \to y_0} f(x,y)$$
Будем считать, что $\varphi(x)$ определена для каждого значения $x$. Тогда рассмотрим предел:
$$A = \lim_{x \to x_0} \varphi(x)$$
Если предел существует, то $A$ - повторный предел функции $f(x,y)$ в точке $(x_0, y_0)$:
$$A = \lim_{x \to x_0} \lim_{y \to y_0} f(x,y)$$
Можно поменять порядок и тоже получить повторный предел, но вообще говоря, он будет другим:
$$B = \lim_{y \to y_0} \lim_{x \to x_0} f(x,y)$$
Это определение можно расширить и до функции нескольких переменных - повторным пределом будет называться такая цепочка пределов по каждой переменной.
## Равенство пределов
Если существует двойной предел $f(x,y)$ в точке $(x_0, y_0)$:
$$\lim_{(x,y) \to (x_0, y_0)} f(x,y) = A$$
и при этом для всех $x$ в проколотой окрестности $x_0$ существует предел:
$$\varphi(y) = \lim_{x \to x_0} f(x,y)$$
то существует повторный предел, причем равный двойному:
$$\lim_{y \to y_0} \varphi(y) = \lim_{y \to y_0} \lim_{x \to x_0} f(x,y) = \lim_{(x,y) \to (x_0, y_0)} f(x,y)$$

## Пример повторного предела
$$\lim_{y \to 0} \lim_{x \to 0} \frac{x^2-y^3}{x^2+y^2}$$
Первый шаг - подсчет внутреннего предела. Здесь все просто, ибо нет никакой неопределенности; подставляем $x$ и заканчиваем.
$$\lim_{y \to 0} \lim_{x \to 0} \frac{x^2-y^3}{x^2+y^2} = \lim_{y \to 0} \lim_{x \to 0} \frac{0^2-y^3}{0^2+y^2} = \lim_{y \to 0} -\frac{y^3}{y^2}$$
А теперь решаем для $y \to 0$:
$$\lim_{y \to 0} -\frac{y^3}{y^2} = \lim_{y \to 0} -y = -0 = 0$$
Отсюда вывод:
$$\lim_{y \to 0} \lim_{x \to 0} \frac{x^2-y^3}{x^2+y^2} = 0$$

