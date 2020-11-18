### Математические структуры. Домашнее задание 4.

##### Выполнил: Кузнецов Владимир Михайлович, БПМИ188.

---

**Задача 1.** Являются ли общезначимыми следующие формулы:

**a)** $(\exists x P(x) \to \exist y Q(y) ) \to \exist y \forall x(P(x) \to Q(y))$,

**b)** $(\forall x P(x, x) \wedge \forall x, y, z ((P(x, y) \wedge P(y, z)) \to P(x, z))) \to \forall x, y (P(x, y) \to P(y, x))$.

---

**a)** Изначально заметим, что $(\exists x P(x) \to \exist y Q(y) ) \equiv \overline{(\exists x P(x))} \vee \exist y Q(y) \equiv \forall x \exists y (\overline{P(x)} \vee Q(y))$.<br>А так же $\exist y \forall x (P(x) \to Q(y)) \equiv \exist y \forall x (\overline{P(x)} \vee Q(y))$. Тогда перепишем нашу формулу в виде:
$$
\forall x \exists y (\overline{P(x)} \vee Q(y)) \to \exist y \forall x (\overline{P(x)} \vee Q(y)).
$$
Для доказательства воспользуемся третьим методом с семинара, а именно, предположим, что существует такая модель $M = (D, P_M, Q_M)$, что вся формула опровергается, т.е. посылка истина, а заключение ложно. Рассмотрим формулу и заметим, что и в посылке часть, которая зависит от $x$ и часть, которая зависит от $y$ не влияют друг на друга. Это значит, что посылка может быть истиной только в двух случаях (или когда выполняются оба одновременно):

1. $\forall x \overline{P(x)}$.
2. $\exists x Q(x)$.

При этом мы получаем истинность заключения при любом случае. Пришли к противоречию, значит, что формула общезначима.

**b)** Рассмотрим $M = (\N, P(x, y) \Leftrightarrow x \geq y)$, тогда
$$
\left.
	\begin{matrix}
		\left.
            \begin{matrix}
                \forall x (x \geq x) \equiv 1 \\
                \forall x, y, z ((x \geq y, y \geq z) \Rightarrow x \geq z) \equiv 1
            \end{matrix}
        \right\}
        \Rightarrow \forall x P(x, x) \wedge \forall x, y, z ((P(x, y) \wedge P(y, z)) \to P(x, z)) \equiv 1 \\
        \forall x, y (x \geq y \Rightarrow y \geq x) \equiv 0 \Rightarrow \forall x, y (P(x, y) \to P(y, x)) \equiv 0 \\
       	1 \to 0 \equiv 0
    \end{matrix}
\right\} \Rightarrow \\
\Rightarrow (\forall x P(x, x) \wedge \forall x, y, z ((P(x, y) \wedge P(y, z)) \to P(x, z))) \to \forall x, y (P(x, y) \to P(y, x)) \equiv 0.
$$
Значит, формула не является общезначимой.

---