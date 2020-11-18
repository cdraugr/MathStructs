### Математические структуры. Домашнее задание 3.

##### Выполнил: Кузнецов Владимир Михайлович, БПМИ188.

---

**Задача 1.** Является ли интуиционистской тавтологией следующая формула:
$$
((\neg \neg p \to p) \to (p \vee \neg p)) \to (\neg p \vee \neg \neg p)?
$$

---

Знаем, что
$$
\not \models ((\neg \neg p \to p) \to (p \vee \neg p)) \to (\neg p \vee \neg \neg p)
\Leftrightarrow
\begin{cases}
	\models (\neg \neg p \to p) \to (p \vee \neg p) \\
	\not \models (\neg p \vee \neg \neg p)
\end{cases}
\Leftrightarrow
\begin{cases}
	\models (\neg \neg p \to p) \to (p \vee \neg p) \\
	\not \models \neg p \\
	\not \models \neg \neg p
\end{cases}.
$$
Тогда, рассмотрим множество из модели Крипке: $W = {a, b, c}$ на котором установлен порядок: $a \preceq b, a \preceq c$. А так же $a \not \models p, b \models p, c \models \neg p$.

При этом можем установить два следствия:

1. $b \models p, a \preceq b \Rightarrow a \not \models \neg p$.
2. $c \models \neg p, a \preceq c \Rightarrow a \not \models \neg \neg p$.

$\Rightarrow \not \models (\neg \neg p \to p) \Rightarrow \models (\neg \neg p \to p) \to (p \vee \neg p)$. Значит, в нашей модели так же $\not \models ((\neg \neg p \to p) \to (p \vee \neg p)) \to (\neg p \vee \neg \neg p)$, а значит исходная формула не является и-тавтологией.

---

