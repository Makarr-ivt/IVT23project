Слово "перестановки" говорит за себя - перестановка множества это произвольный упорядоченный набор *всех* элементов этого множества. $\set{5,1,3,4,2,6}$ - перестановка множества $\set{1,2,3,4,5,6}$. 

Перестановка является частным случаем размещений при $n=k$. Опять же с кубиками, мы хотим разместить $n$ кубиков на $n$ слотов, и с каждым новым слотом количество кубиков для выбора падает.
$$P_n = A^n_n = \frac{n!}{(n-n)!} = \frac{n!}{0!}=\frac{n!}1=n!$$

Перестановки с повторениями уже посложнее. Скажем, в множестве из $n$ элементов есть $k$ повторяющихся (идентичных) элементов. Тогда, составляя перестановки множества, какая-то часть этих перестановок будут совпадать друг с другом. Например, вот все перестановки элементов множества $\set{A_1, A_2, B}$
$$\array{\set{A_1, A_2, B} & \set{A_2, A_1, B} \\ \set{A_1, B, A_2} & \set{A_2, B, A_1} \\ \set{B, A_1, A_2} & \set{B, A_2, A_1}}$$
Если бы я не поставил индексы для $A$, то левая половина перестановок ничем бы не отличалась от правой половины. Значит, на деле перестановок не 6, а 3. А сколько всего будет таких повторений? Для каждой перестановки будет столько повторений, сколько существует перестановок этих самых повторяющихся элементов. Здесь элемента было 2, и количество перестановок двух элементов $P_2 = 2! = 2$. Значит, для каждой перестановки существует своя идентичная пара.

Чтобы избавиться от учитывания повторов, нужно поделить количество всех перестановок на количество повторяющихся:
$$\frac{n!}{k!}$$
Если существует две, три, четыре и т.д. группы одинаковых элементов - делим на количество перестановок каждой из этих групп - и получается общая формула для перестановок с повторениями:
$$\binom n{k_1, k_2, \ldots, k_m} = \frac{n!}{k_1!k_2!\ldots k_m!}$$

## Примеры задач

> Сколькими способами 8 студентов может выстроиться в очередь на защиту экзамена по физике?

Все студенты уникальны между собой, так что количество способов будет просто равно количеству перестановок:
$$P_8 = 8! = 40320$$
> Сколько есть способов переставить буквы в слове ФИЗИКА?

Обращаем внимание на повторяющиеся буквы "И" (их две) - значит, общее количество перестановок нужно поделить на количество перестановок двух букв "И":
$$\binom 6 2 = \frac{6!}{2!} = 6 \cdot 5 \cdot 4 \cdot 3 = 360$$