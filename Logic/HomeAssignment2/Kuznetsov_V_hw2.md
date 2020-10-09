### Математические структуры. Домашнее задание 2.

##### Выполнил: Кузнецов Владимир Михайлович, БПМИ188.

---

**Задача 1.** Постройте вывод секвенции $\Rightarrow (p \to q) \to ((\neg p \to q) \to q)$.

---

$$
\dfrac{\dfrac{\dfrac{p \to q, q \Rightarrow q \quad \quad p \to q \Rightarrow q, \neg p \quad (\to L)}{p \to q, \neg p \to q \Rightarrow q \quad (\to R)}}{p \to q \Rightarrow (\neg p \to q) \to q \quad (\to R)}}{\Rightarrow (p \to q) \to ((\neg p \to q) \to q)}
$$

Будем рассматривать вершины отдельно:
$$
\begin{matrix}
\dfrac{ q, q \Rightarrow q \quad \quad q \Rightarrow q, p}{q, p \to q \Rightarrow q} (\to L); &
\dfrac{\dfrac{p, q \Rightarrow q \quad \quad p \Rightarrow q, p \quad (\to L)}{p \to q, p \Rightarrow q \quad (\neg R)}}{p \to q \Rightarrow q, \neg p}.
\end{matrix}
$$
Получили четыре аксиомы, значит вывод построен.

---

**Задача 2.** Докажите, что следующая секвенция невыводима $\Rightarrow (p \to q) \to \neg p$.

---

$\triangleright\quad$ Изначально имеем только один шаг:
$$
\dfrac{p \to q \Rightarrow \neg q}{\Rightarrow (p \to q) \to \neg p} (\to R).
$$
Теперь рассмотрим разветвление:
$$
\begin{matrix}
\dfrac{q \Rightarrow \neg q \quad \quad \Rightarrow \neg q, p}{p \to q \Rightarrow \neg q} (\to L); &
\dfrac{p \to q, q \Rightarrow}{p \to q \Rightarrow \neg q} (\neg R).
\end{matrix}
$$
Как нам известно с семинара, $q \Rightarrow \neg q$ $-$ невыводима, значит левый вариант мы не рассматриваем. Продолжим рассматривать правый:
$$
\dfrac{q, q \Rightarrow \quad \quad q \Rightarrow p}{p\to q, q \Rightarrow} (\to L).
$$
Дальше раскладывать некуда, а аксиом не вышло. $\quad\square$

---