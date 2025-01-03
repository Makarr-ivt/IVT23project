*Разрез транспортной сети* - пара непересекающихся множеств $\langle A, B \rangle$, что $V = A \cup B$ и $s \in A$ и $t \in B$.
Грубо говоря ножом провели по транспортной сети, между источником и стоком - стало две частички - это и есть $A$ и $B$.

Имеется и другое определение разреза - подмножество ребер $\delta(X) \subset V$, которое принадлежит $A$, но не принадлежит $B$. Вместо того, чтобы определять разрез как два кусочка, это определение берет во внимание все ребра, которые попали под нож.

*Пропускная способность разреза* определяется как сумма всех пропускных способностей ребер разреза:
$$c(\delta(X)) = c(A,B) = \sum_{(u,v) \in \delta(X)} c(u,v) = \sum_{(u,v) \in E, u \in A, v \in B} c(u,v)$$
Аналогично определяется *величина потока разреза*:
$$f(\delta(X)) = f(A, B) = \sum_{(u,v) \in \delta(X)} f(u,v) = \sum_{(u,v) \in E, u \in A, v \in B} f(u,v)$$
*Минимальный разрез* - разрез с минимальной пропускной способностью.

Поток через любой разрез равен сумме потоков из источника и равен сумме потоков в сток = $|f|$. Рассмотрим сумму всех потоков из вершин $A$ - разделим ее на сумму из вершин $A$ в вершины $A$ и сумму из вершин $A$ в вершины $B$ (так как $A\cup B = V$ и они не пересекаются):
$$\sum_{u \in A} \sum_{v \in V} f(u,v) = \sum_{u \in A} \sum_{v \in A} f(u,v) + \sum_{u \in A} \sum_{v \in B} f(u,v)$$
Первая сумма равна нулю, ведь для каждого $f(u,v)$ найдется $f(v,u)$, а они противоположны по знаку. Для суммы слева, $f(u,v)$ равна нулю, если $u \neq s$ или $u \neq t$. Но $t \notin A$, поэтому
$$\sum_{v \in V} f(s,v) = 0 + \sum_{u \in A} \sum_{v \in B} f(u,v) \Rightarrow$$
$$\sum_{(u,v) \in E, u \in A, v \in B} f(u,v) = |f|$$

