Авторство: @pavel_hludin

>[!warning] При составлении билета использовался ChatGPT.

Формулы Френеля описывают, как амплитуды или интенсивности света делятся между отраженным и преломленным светом при падении на границу раздела двух сред.

Обозначения:
- $n_1, n_2$ - показатели преломления первой и второй среды,
- $\theta_i$ - угол падения,
- $\theta_t$ - угол преломления (определяется законом Снелля: $n_1 \sin \theta_i = n_2 \sin \theta_t$).

Формулы для амплитуд отраженной и преломленной среды зависят от типа поляризации:
1. Поляризация $s$ (свет поляризован перпендикулярно плоскости падения):
- Коэффициент отражения: $$r_s = \frac{n_1 \cos \theta_i - n_2 \cos \theta_t}{n_1 \cos \theta_i + n_2 \cos \theta_t}$$
- Коэффициент пропускания: $$t_s = \frac{2n_1 \cos \theta_i}{n_1\cos \theta_i + n_2\cos \theta_t}$$
2. Поляризация $p$ (свет поляризован в плоскости падения):
- Коэффициент отражения: $$r_p = \frac{n_2 \cos \theta_i - n_1 \cos \theta_t}{n_2 \cos \theta_i + n_1 \cos \theta_t}$$
- Коэффициент пропускания: $$t_p = \frac{2n_1 \cos \theta_i}{n_2\cos \theta_i + n_1\cos \theta_t}$$
Коэффициенты интенсивности отраженного $R$ и преломленного $T$ света находятся как квадраты амплитудных коэффициентов:
$$R_s = |r_s|^2, \quad R_p = |r_p|^2, \quad T_s = |t_s|^2, \quad T_p = |t_p|^2$$

## Закон Брюстера
Закон Брюстера определяет угол падения, при котором отраженный свет полностью поляризован ($r_p = 0$). Угол Брюстера $\theta_B$ связан с показателями преломления следующим образом:
$$\tg \theta_B = \frac{n_2}{n_1}$$
При $\theta_i = \theta_B$ отраженный свет становится полностью поляризованным перпендикулярно плоскости падения.

## Поведение фазы при отражении
При отражении света фаза волны может измениться на $180^\circ$ ($\pi$) или остаться неизменной, в зависимости от направления перехода:
- Переход из оптически менее плотной среды в более плотную ($n_1 < n_2$): отраженный свет приобретает сдвиг фазы $\pi$.
- Наоборот, при переходе из более плотной фазы в менее плотную, свдиг фазы отсутствует.

Для $p$-поляризации угол Брюстера соответствует условию, при котором фаза отраженного света меняется на $90^\circ$.