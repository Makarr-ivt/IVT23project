Логика буля, или же булевая алгебра, или же алгебра логики, оперирует над переменными, которые могут принимать только значения 0/ложь и 1/истина. Основными операторами являются конъюнкция ("и", $\wedge$), дизъюнкция ("или", $\vee$) и отрицание ("не", $\overline{}$ ).

Приоритет операций: первым выполняется отрицание, потом конъюнкция, в конце дизъюнкция.

Существует нотация, где конъюнкция заменяется умножением $(\cdot)$, а дизъюнкция - сложением $(+)$. Только в таком случае нужно условиться, что $1+1=1$. Также символ конъюнкции иногда пропускается, и операнды записываются слитно: $A \wedge B = AB$.

Поведение операторов в алгебре логике принято записывать через таблицы истинности - таблицы, в которых указан результат оператора для всевозможных входных значений. Это возможно сделать из-за конечного числа значений, принимаемых переменными.

Выражение, составленное из операторов и переменных, называется логической функцией, и чтобы составить таблицу для функции от $n$ переменных, нужно $2^n$ строчек.

Вместе с операторами будем приводить их использование над естественными высказываниями:

$A$ = "На улице идет дождь",
$B$ = "Над моей головой раскрыт зонт"

## Основные операторы
Отрицание - унарный оператор - можно определить с помощью следующей таблицы:

| $A$ | $\overline A$ |
| --- | ------------- |
| 0   | 1             |
| 1   | 0             |

$\overline A$ = "На улице не идет дождь"

Конъюнкция принимает истину только когда оба операнда истинны:

| $A$ | $B$ | $A \wedge B$ |
| --- | --- | ------------ |
| 0   | 0   | 0            |
| 0   | 1   | 0            |
| 1   | 0   | 0            |
| 1   | 1   | 1            |

$A \wedge B$ = "На улице идет дождь и над моей головой раскрыт зонт"

Дизъюнкция же наоборот, истинна когда хоть один из операндов истин:

| $A$ | $B$ | $A \vee B$ |
| --- | --- | ---------- |
| 0   | 0   | 0          |
| 0   | 1   | 1          |
| 1   | 0   | 1          |
| 1   | 1   | 1          |

$A \vee B$ = "На улице идет дождь или над моей головой раскрыт зонт"

И это главных три оператора - главных в том смысле, что на основе них можно составить любой другой оператор. А теперь мы пойдем в лес производного говна.

## Производная параша
Импликация: самая распространенная производная операция. Ложно лишь тогда, когда $A$ истинно, а $B$ ложно (по смыслу, импликация это причинно-следственная связь, и в этом случае она нарушается)
$$(A \to B) = \overline A \vee B$$

| $A$ | $B$ | $A \to B$ |
| --- | --- | --------- |
| 0   | 0   | 1         |
| 0   | 1   | 1         |
| 1   | 0   | 0         |
| 1   | 1   | 1         |

$A \to B$ = "Если на улице идет дождь, то над моей головой раскрыт зонт"

Эквивалентность: истинна лишь тогда, когда операторы равны по значению.
$$(A \iff B) = (A \equiv B) = (A \leftrightarrow B) = (A \sim B) = (\overline A \wedge \overline B) \vee (A \wedge B)$$

| $A$ | $B$ | $A \iff B$ |
| --- | --- | ---------- |
| 0   | 0   | 1          |
| 0   | 1   | 0          |
| 1   | 0   | 0          |
| 1   | 1   | 1          |

$A \iff B$ = "На улице идет дождь тогда и только тогда, когда (титтк) над моей головой раскрыт зонт"

Исключающее или: аналог оборота "либо ..., либо ...". Истинна лишь когда только один из операндов истин.
$$(A \oplus B) = (A \neq B) = A ^\wedge B = (\overline A \wedge B) \vee (A \wedge \overline B) = (\overline A \vee \overline B) \wedge (A \vee B)$$

| $A$ | $B$ | $A \oplus B$ |
| --- | --- | ------------ |
| 0   | 0   | 0            |
| 0   | 1   | 1            |
| 1   | 0   | 1            |
| 1   | 1   | 0            |

$A \oplus B$ = "Либо на улице идет дождь, либо над моей головой раскрыт зонт"

Штрих Шеффера: учимся говорить нормальным языком: "И-НЕ", "NAND" - отрицание конъюнкции. NAND оператор способен с нуля собрать любой другой логический оператор - на данный процесс есть игра: https://nandgame.com.
$$A \uparrow B = A \vert B = \overline {(A \wedge B)} = \overline A \vee \overline B$$

| $A$ | $B$ | $A \uparrow B$ |
| --- | --- | -------------- |
| 0   | 0   | 1              |
| 0   | 1   | 1              |
| 1   | 0   | 1              |
| 1   | 1   | 0              |

$A \uparrow B$ = "На улице не идет дождь или над моей головой не раскрыт зонт"

Стрелка Пирса: еще более бесполезный, чем штрих Шеффера. Опять же, учимся говорить нормальным языком: "ИЛИ-НЕ", "NOR" - отрицание дизъюнкции.
$$A \downarrow B = \overline{(A \vee B)} = \overline A \wedge \overline B$$

| $A$ | $B$ | $A \downarrow B$ |
| --- | --- | ---------------- |
| 0   | 0   | 1                |
| 0   | 1   | 0                |
| 1   | 0   | 0                |
| 1   | 1   | 0                |

$A \downarrow B$ = "На улице не идет дождь и над моей головой не раскрыт зонт"

Обратная импликация и вовсе не заслуживает внимания.