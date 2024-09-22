Условие: найти точки $M$ гиперболы, заданной уравнением
$$\frac{x^2}{36} - \frac{y^2}{9} = 1$$
расстояние от которых до левого фокуса равно $8$.

Решение:
Сначала выпишем $a$ и $b$ из канонического уравнения (знаменатели):
$a = \sqrt{36} = 6$
$b = \sqrt 9 = 3$
Обратите на разницу формулу эксцентриситета для эллипса и гиперболы:
$$e = \sqrt{1 + \frac{b^2}{a^2}} = \sqrt{1 + \frac{9}{36}} = \frac{\sqrt{45}}{6}$$
Расстояние от точки $M$ на гиперболе до фокусов $F_1$ и $F_2$ определяется по формулам:
$$r_1 = |a - ex| \ \ \ \ \ \ \ \ \ \ \ r_2 = |a+ex|$$
$r_2$ принимает минимальное значение при $x<0$, а значит оно отвечает за левый фокус (ведь он находится в левой половине координатной системы). Находим $x$ для этого фокуса:
$$8 = |6 + \frac{\sqrt{45}}6x|$$
$$\left[\array{8 = 6 + \frac{\sqrt{45}}6x \\ -8 = 6 + \frac{\sqrt{45}}6x}\right. \Rightarrow \left[\array{x = \frac{12}{\sqrt{45}} = \frac{4}{\sqrt5}\\ x = \frac{-14\cdot6}{\sqrt{45}} = -\frac{28}{\sqrt5}}\right.$$
Теперь, чтобы найти $y$, нужно просто подставить $x$ в уравнение гиперболы и решить на $y$.
Однако, одно из этих значений ложно. $4/\sqrt{5} < 6$, поэтому
$$\frac{x^2}{36} < 1 \ \ \ \ \ \ \text{     при } x=\frac{4}{\sqrt 5}$$
Это значит, что в уравнении гиперболы не существует действительных корней для $y$. Решаем только для $x = -28/\sqrt{5}$.
$$\frac{x^2}{36} - \frac{y^2}{9} = 1 \Rightarrow y^2 = 9\left(\frac{x^2}{36} -1\right)$$
$$y^2 = 9\left(\frac{28^2}{36\cdot 5} -1\right) = \frac{28^2}{20} - 9 = \frac{14^2}{5} - 9 = \frac{151}{5}$$

Ответ: $M = \left(-\frac{28}{\sqrt 5}, \pm \sqrt{\frac{151}5}\right)$

---
Условие: найти точки $M$ гиперболы, заданной уравнением
$$\frac{x^2}{9} - \frac{y^2}{16} = 1$$
расстояние от которых до левого фокуса равно $7$.

Решение:
Шаг первый: выделить коэффициенты $a,b$, найти эксцентриситет.
$a = \sqrt 9 = 3$
$b = \sqrt{16} = 4$
$$e = \sqrt{1 + \frac{b^2}{a^2}} = \frac{5}{3}$$
Шаг второй: решить уравнение для расстояния до фокуса. Мы выбираем формулу
$$r_2 = |a+ex|$$
по аналогичной логике как в прошлом задании.
$$7 = |3 + \frac53 x|$$
$$\left[\array{7 = 3 + \frac53 x \\ -7 = 3 + \frac53 x}\right. \Rightarrow \left[\array{x = \frac{14}5 \\ x = -6}\right.$$
Шаг третий: отсеять ложное значение. Обычно это наименьшее значение, и действительно:
$$14/5 < 3 \Rightarrow \frac{x^2}{9} < 1$$
Решаем только для $x=-6$.
$$y^2 = 16\left(\frac{x^2}9 - 1\right) = 16\left(\frac{36}9 - 1\right) = 48$$

Ответ: $M = \left(-6; \pm 4\sqrt3 \right)$

---
Условие: найти точки $M$ гиперболы, заданной уравнением
$$\frac{x^2}{4} - \frac{y^2}{9} = 1$$
расстояние от которых до правого фокуса равно $6$.

Решение:
Шаг первый: выделить коэффициенты $a,b$, найти эксцентриситет.
$a = \sqrt 4 = 2$
$b = \sqrt{9} = 3$
$$e = \sqrt{1 + \frac{b^2}{a^2}} = \frac{\sqrt {13}}{2}$$
Шаг второй: решить уравнение для расстояния до фокуса. Теперь, т.к. фокус правый, мы берем другую формулу:
$$r_1 = |a - ex|$$
Находим $x$:
$$6 = |2 - \frac{\sqrt{13}}2 x|$$
$$\left[\array{6 = 2 - \frac{\sqrt{13}}2 x \\ -6 = 2 - \frac{\sqrt{13}}2 x}\right. \Rightarrow \left[\array{x = -\frac{8}{\sqrt{13}} \\ x = \frac{16}{\sqrt{13}}}\right.$$
Шаг третий: отсеять ложное значение.
$$-8/\sqrt{13} > 2 = 8/\sqrt{16}$$
Ложного значения нет! Считаем для двух значений - эти точки будут лежать на разных ветвях.
$$\frac{x^2}{4} - \frac{y^2}{9} = 1 \Rightarrow y^2 = 9\left(\frac{x^2}4 - 1\right)$$
Для $x=-8/\sqrt{13}$:
$$y^2 = 9\left(\frac{64}{4\cdot 13} - 1\right) = 9\left(\frac{16}{13} - 1\right) = \frac{27}{13}$$
Для $x = 16/\sqrt{13}$:
$$y^2 = 9\left(\frac{16 \cdot 16}{4\cdot 13} - 1\right) = 9\left(\frac{64}{13} - 1\right) = \frac{51 \cdot 9}{13} = \frac{459}{13}$$

Ответ: $M_1 = (-\frac{8}{\sqrt{13}}, \pm \frac{\sqrt{27}}{\sqrt{13}})$, $M_2 = (\frac{16}{\sqrt{13}}, \pm \frac{\sqrt{459}}{\sqrt{13}})$