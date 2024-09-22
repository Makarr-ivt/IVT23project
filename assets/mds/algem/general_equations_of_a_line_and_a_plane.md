## Прямая
Общее уравнение прямой записывается как
$$Ax + By + C=0$$
Где $A, B, C$ - вещественные числа.

Чем плоха запись через угловой коэффициент, $y=ax+b$? Да тем, что у $y$ нет коэффициента, поэтому нельзя создать чисто вертикальную прямую (для этого бы потребовался $a = \infty$)
К счастью, перевести в общее уравнение прямой такую запись легко, просто все в одну сторону сносим:
$$-ax + y - b = 0$$
$$A = -a; B = 1; C = -b$$

Если нам даны две точки, $P_1 = (x_1; y_1)$ и $P_2 = (x_2; y_2)$, как по ним составить уравнение прямой? (ведь любые две различные точки однозначно задают прямую)
Для этого воспользуемся смыслом определителя матрицы второго порядка:
Скажем, что у нас есть точка $P_3 = (x; y)$. Если эта точка лежит на прямой $P_1P_2$, то площадь параллелограмма, образованного этими тремя точками (или же векторами $P_1P_2$ и $P_1P_3$) будет равна нулю. Это равносильно условию, что векторное произведение этих векторов равно нулю. Это же равносильно тому, что определитель матрицы из этих векторов будет равен нулю. Соберем эту матрицу, для начала сместив все точки так, что $P_1$ окажется в нуле.
$P_2' = (x_2-x_1; y_2-y_1)$
$P_3' = (x-x_1; y-y_1)$
Тогда, решим:
$$\left|\matrix{x_2-x_1 & y_2-y_1 \\ x-x_1 & y-y_1}\right| = 0$$
$$(x_2-x_1)(y-y_1) - (y_2-y_1)(x-x_1) =$$
$$= x_2y-x_2y_1-x_1y+\cancel{x_1y_1} -y_2x+y_2x_1+y_1x-\cancel{y_1x_1} =$$
$$x(y_1-y_2)+y(x_2-x_1)+x_1y_2 - x_2y_1 = 0$$
Полагаем $A = y_1 - y_2, B = x_2-x_1, C= x_1y_2 - x_2y_1$ и получаем наше уравнение $Ax+By+C=0$.

Как найти вектор нормали (вектор, что будет перпендикулярен) к прямой в общем виде? Для прямой $Ax+By+C=0$, такой вектор будет $\overline n(A; B)$.

На деле нормаль связана с этими коэффициентами самым естественным способом из-за скалярного произведения. Если задать вектор нормали $(A;B)$, и приравнять скалярное произведение с общим вектором $(x;y)$ к нулю, то мы получим прямую:
$$((x;y), (A; B)) = 0 \Leftrightarrow Ax+By=0$$
Это такая прямая, что если мы возьмем вектор из центра координат до любой точки на прямой, этот вектор будет перпендикулярен вектору $(A;B)$. А так как смещение прямой на константу не меняет наклон прямой, то $Ax+By+C=0$ так же будет перпендикулярна нормальному вектору.

Коллинеарный вектор, кстати, будет $\overline p(-B, A)$ - просто $\overline n$ повернутый на 90 градусов. Попробуйте сами повращать любую точку на плоскости на 90 градусов влево и увидите как меняются ее координаты соответственно.
![[algem-15-1.png]]
С другой стороны, при подстановке $-B$ и $A$ в уравнение $Ax + By = 0$ оно будет верным, поэтому точка (что по сути будет вектор) будет принадлежать прямой без $C$. Эта константа не влияет, ибо векторы спокойно можно перемещать.

## Плоскость
Общее уравнение плоскости записывается следующим образом:
$$Ax+By+Cz+D=0$$
Похоже на прямую, не так ли?)
Как и с нормальным вектором для прямой, вектор нормали для плоскости будет $\overline n(A; B; C)$, причем по той же причине, что была описана для прямой.

Давайте займемся построениями плоскостей.
Самое стандартное условие, дано три точки: $M_1(x_1, y_1, z_1)$, $M_2(x_2, y_2, z_2)$, $M_3(x_3, y_3, z_3)$. Построить уравнение плоскости, которая содержит все эти точки.
Как мы знаем, любые три точки, не лежащие на одной прямой, однозначно задают плоскость. Мы будем действовать, как и с плоскостью: по смыслу, как векторное произведение задавало площадь параллелограмма, так смешанное произведение задаст объем параллелепипеда. Если объем параллелепипеда, состоящего из трех векторов, равен нулю, то эти векторы лежат в одной плоскости.
Начнем смещать точки (считать вектора) чтобы подвести их под смешанное произведение:
$M_1' = M_1 - M_1 = (0;0;0)$
$M_1M_2 = M_2 - M_1 = (x_2 - x_1; y_2 - y_1; z_2 - z_1)$
$M_1M_3 = M_3 - M_1 = (x_3 - x_1; y_3 - y_1; z_3 - z_1)$
$M_1M_4 = (x - x_1; y - y_1; z - z_1)$
Теперь с помощью векторов составляем смешанное произведение через определитель (см. вопрос [[#13. Выражение смешанного произведения через координаты сомножителей.]]) и приравниваем к нулю:
$$(M_1M_4, M_1M_2, M_1M_3) = \left|\array{x-x_1 & y-y_1&z-z_1 \\ x_2-x_1 & y_2 - y_1 & z_2-z_1 \\ x_3-x_1 & y_3-y_1 & z_3-z_1}\right| = 0$$
Теперь осталось просто посчитать определитель этого, и мы получим уравнение для плоскости. Делать я этого, конечно, не буду, ибо в буквах я просто устану это делать, да и это ничего интересного не покажет.

Соответствующая схема работает если дана одна точка и два вектора, и нужно построить плоскость по этим данным. Тогда мы просто пропускаем построения некоторых векторов (когда мы смещали точки).

## Пример задачи
Условие: найдите уравнение прямой в общем виде, проходящую через точки $A(4; 7)$ и $B(-3; 12)$.

Решение: строим векторы.
$\overline a = (x;y) - A = (x-4; y-7)$
$\overline b = B - A = (-3-4; 12-7) = (-7; 5)$
Приравниваем определитель к нулю, чтобы площадь параллелограмма была равна нулю:
$$\left|\array{x-4 & y-7 \\ -7 & 5}\right| = 0$$
$$5(x-4) + 7(y-7) = 0$$
$$5x+7y-69=0$$

---
Условие: найдите уравнение плоскости в общем виде, проходящую через точки $A(4; 3; 9), B(-2; 6; 8), C(-2; 8; 5)$.

Решение: строим векторы!
$\overline a = (x;y;z) - A = (x-4; y-3; z-9)$
$\overline b = B - A = (-2-4; 6-3; 8-9) = (-6;3;-1)$
$\overline c = C - A = (-2-4; 8-3; 5-9) = (-6; 5; -4)$
Приравниваем определитель к нулю, чтобы объем параллелипипеда был равен нулю:
$$\left|\array{x-4 & y-3 & z-9 \\ -6 & 3 & -1\\ -6 & 5 & -4}\right| = 0$$
$$(x-4)(-12+5) - (y-3)(24+6) + (z-9)(-30+18)=0$$
$$-7x-30y-12z+226=0$$
Чтобы выглядело нормально, делаем коэффициент $A$ положительным - умножаем на $-1$:
$$7x+30y+12z-226=0$$