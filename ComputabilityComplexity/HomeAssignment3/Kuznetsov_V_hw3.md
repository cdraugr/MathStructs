### Математические структуры.

#### Кузнецов Владимир Михайлович, ФКН.

---

##### <p align=center> Контрольная работа 2. Вариант 2.<p>

---

**Задача 1.** Верно ли, что $K \leq_m P = \{n \in \N| n$ простое$\}$,где $K = \{n \in \N| \varphi_n(n)\downarrow\}$?

---

Нет, не верно. Знаем, что если существуют два множества $A,B\subseteq \N$ таких что $A \leq_m B$ и $B$ рекурсивно $\Rightarrow A$ рекурсивно. При этом достаточно просто видно, что множество $P$ $-$ рекурсивно, так как явно можем описать $\chi_P(x) \iff \neg(\exists y \ne x, z\ne x : y \cdot z = x)$, но при этом про нерекурсивность множества $K$ мы знаем с лекций, а значит, если бы существовала такая функция $f(x)$, что $x \in K \iff f(x) \in P$, то мы бы приходили к противоречию.

---

**Задача 2.** Расставьте все скобки в следующих $\lambda$-термах и выполните подстановку $M[x := N]$, предварительно переименовав связанные переменные (если потребуется) так, чтобы подстановка стала допустимой:
$$
M = (\lambda y.x(\lambda xz.xxz)(yx))(\lambda yz.xz(\lambda x.x))z,\quad N = x(\lambda z.zy).
$$

---

$$
\begin{multline}
M = (\lambda y.x(\lambda xz.xxz)(yx))(\lambda yz.xz(\lambda x.x))z = \\
 = \left( \Bigg( \bigg( \lambda y. \Big( \big( x (\lambda x .( \lambda z.((xx)z))) \big) (yx) \Big) \bigg) \bigg( \lambda y.(\lambda z.((xz)(\lambda x.x))) \bigg) \Bigg) z \right) = \\
= \left( \Bigg( \bigg( \lambda u. \Big( \big( x (\lambda x .( \lambda v.((xx)v))) \big) (ux) \Big) \bigg) \bigg( \lambda y.(\lambda v.((xv)(\lambda x.x))) \bigg) \Bigg) z \right),
\end{multline} \\
N = x(\lambda z.zy) \Rightarrow N = \Big( x \big( \lambda z.(zy) \big) \Big).
$$

Теперь выполним подстановку, но будем выполнять поочереди, а то совсем помрём. Зададим
$$
P = \bigg( \lambda u. \Big( \big( x (\lambda x .( \lambda v.((xx)v))) \big) (ux) \Big) \bigg), \quad Q = \bigg( \lambda y.(\lambda v.((xv)(\lambda x.x))) \bigg).
$$
Заметим, что $M = ((PQ)z)$, тогда $M[x:=N] = ((P[x:=N]Q[x:=N])z)$.<br>Теперь отдельно рассмотрим $P[x:=N]$ и $Q[x:= N]$:
$$
\begin{align}
P[x:=N] = \bigg( \lambda u. \Big( \big( x (\lambda x .( \lambda v.((xx)v))) \big) (ux) \Big) \bigg)[x: = N] = \\
= \bigg( \lambda u. \Big( \big( x (\lambda x .( \lambda v.((xx)v))) \big) (ux) \Big) [x: = N] \bigg) = \\
= \bigg( \lambda u. \Big( \big( x (\lambda x .( \lambda v.((xx)v))) \big)[x: = N] (ux)[x: = N] \Big) \bigg) = \\
= \bigg( \lambda u. \Big( \big( N (\lambda x .( \lambda v.((xx)v))) [x: = N]\big) (uN) \Big) \bigg) = \\
= \bigg( \lambda u. \Big( \big( N (\lambda x .( \lambda v.((xx)v))) \big) (uN) \Big) \bigg) = \\
= \bigg( \lambda u. \Big( \big( \Big( x \big( \lambda z.(zy) \big) \Big) (\lambda x .( \lambda v.((xx)v))) \big) (u\Big( x \big( \lambda z.(zy) \big) \Big)) \Big) \bigg),
\end{align}
$$

$$
\begin{align}
Q[x:=N] = \bigg( \lambda y.(\lambda v.((xv)(\lambda x.x))) \bigg)[x: = N] = \\
= \bigg( \lambda y.(\lambda v.((xv)(\lambda x.x)))[x: = N] \bigg) = \\
= \bigg( \lambda y.(\lambda v.((xv)(\lambda x.x)) [x: = N]) \bigg) = \\
= \bigg( \lambda y.(\lambda v.((xv) [x: = N](\lambda x.x) [x: = N])) \bigg) = \\
= \bigg( \lambda y.(\lambda v.((Nv)(\lambda x.x))) \bigg) = \\
= \bigg( \lambda y.(\lambda v.((\Big( x \big( \lambda z.(zy) \big) \Big)v)(\lambda x.x))) \bigg).\\
\end{align}
$$

А значит, можем записать итоговый результат в виде:
$$
M[x:=N] = \Bigg( \bigg( \lambda u. \Big( \big( \Big( x \big( \lambda z.(zy) \big) \Big) (\lambda x .( \lambda v.((xx)v))) \big) (u\Big( x \big( \lambda z.(zy) \big) \Big)) \Big) \bigg) \bigg( \lambda y.(\lambda v.((\Big( x \big( \lambda z.(zy) \big) \Big)v)(\lambda x.x))) \bigg) z \Bigg).
$$

---

**Задача 3.** Приведите $\lambda$-терм $SS(SK)$, где $S = \lambda xyz.xz(yz)$ и $K = \lambda xy.x$, к $\beta$-нормальной форме.

---

Имеем $SS(SK) = ((SS)(SK))$, где $S = (\lambda x.(\lambda y. (\lambda z.((xz)(yz)))))$ и $K = (\lambda x.(\lambda y.x))$.

Давайте изначально отдельно рассмотрим $SS$, потом $SK$, а потом $((SS)(SK))$.
$$
\begin{multline}
SS = (\lambda x . \underbrace{(\lambda yz.xz(yz))}_{M})\underbrace{(\lambda xyz.xz(yz))}_N \to_\beta (\lambda uv.xv(uv))[x := \lambda xyz.xz(yz)] = \\
= \lambda uv.((\lambda x . \underbrace{(\lambda yz.xz(yz))}_{M})\underbrace{v}_{N})(uv) \to_{\beta} \lambda uv.\Big( (\lambda y . \underbrace{( \lambda z.vz(yz))}_{M})\underbrace{(uv)}_{N} \Big) 
\to_{\beta} \lambda uvz.vz(uvz),
\end{multline}
$$

$$
\begin{multline}
SK = (\lambda x . \underbrace{(\lambda yz.xz(yz))}_{M})\underbrace{(\lambda xy.x)}_N \to_\beta (\lambda uz.xz(uz))[x := \lambda xy.x] = \\
= \lambda u z.((\lambda x. \underbrace{(\lambda y.x)}_{M})\underbrace{z}_{N}(uz)) \to_{\beta} \lambda uz.(\lambda y. \underbrace{z}_{M})\underbrace{(uz)}_{N} \to_\beta \lambda uz . z.
\end{multline}
$$

А это значит, что
$$
\begin{multline}
SS(SK) \twoheadrightarrow_{\beta} (\lambda u . \underbrace{(\lambda vz.vz(uvz))}_{M})\underbrace{(\lambda uz.z)}_{N} \to_{\beta} \lambda va.va(((\lambda u . \underbrace{(\lambda z.z)}_{M})\underbrace{v}_{N})a) \to_{\beta} \\
\to_{\beta} \lambda va.va((\lambda z.\underbrace{z}_{M})\underbrace {a}_{N}) \to_{\beta} \lambda va . vaa = (\lambda v. ( \lambda a . ((va)a))).
\end{multline}
$$

---

**Задача 4.** Докажите, что $\lambda$-терм $\lambda xy.(M(Nxy))$, где $M = \lambda zxy.zyx$ и $N = \lambda xy.xyx$, представляет булеву функцию $f(x,y) = \neg(x \wedge y)$.

---

$\triangleright\quad$ Тактика в этом номере проста. Изначально введём два комбинатора $\text F = \lambda xy.y = (0)^*$ и $\text T = \lambda xy.x = (1)^*$. Теперь рассмотрим $((Nx)y)$, приведём его к $\beta$-нормальной форме, а дальше продолжим работу с $\lambda xy.(M(Nxy))$.
$$
Nxy = ((\lambda x. (\lambda y.xyx))x)y) \to_{\beta} (\lambda y.xyx)y \to_{\beta} xyx \Rightarrow \\
\Rightarrow M(Nxy) \twoheadrightarrow_{\beta} M(xyx) = (\lambda z. (\lambda xy.zyx))(xyx) \to_{\beta} \lambda uv.xyxvu.
$$
Теперь нам надо исследовать термы вида $(\lambda xyuv.(xyxvu))PQ \twoheadrightarrow_{\beta} \lambda uv.PQPvu$, где $P, Q \in \{\text T, \text F\}$. Теперь давайте рассмотрим все четыре случая, но изначально выполним подгоовительную работу:
$$
\begin{matrix}
\text{TTT} = (\lambda xy.x)\text{TT} \twoheadrightarrow_{\beta} \text{T}, & \text{FFF} = (\lambda xy.y)\text{FF} \twoheadrightarrow_{\beta} \text{F}, \\
\text{TFT} = (\lambda xy.x)\text{FT} \twoheadrightarrow_{\beta} \text{F}, & \text{FTF} = (\lambda xy.y)\text{TF} \twoheadrightarrow_{\beta} \text{F}.
\end{matrix} \\
$$
Наконец-то, мы готовы осуществить финальное доказательство!
$$
\lambda xy.M(Nxy)\text T \text T \twoheadrightarrow_{\beta} \lambda uv.\text T\text T\text Tvu \twoheadrightarrow_{\beta} \lambda uv.\text Tvu = \lambda uv.((\lambda xy.x)v)u \to_{\beta } \lambda uv (\lambda y.v)u \to_{\beta} \lambda uv.v = \text F = (0)^*, \\

\lambda xy.M(Nxy)\text T \text F \twoheadrightarrow_{\beta} \lambda uv.\text T\text F\text Tvu \twoheadrightarrow_{\beta} \lambda uv.\text F vu = \lambda uv.(\lambda xy.y) vu \to_{\beta} \lambda uv.(\lambda y.y)u \to_{\beta} \lambda uv.u = \text T = (1)^*, \\

\lambda xy.M(Nxy)\text F \text T \twoheadrightarrow_{\beta} \lambda uv.\text F\text T\text Fvu \twoheadrightarrow_{\beta} \lambda uv.\text F vu \twoheadrightarrow_{\beta} \text T = (1)^*, \\

\lambda xy.M(Nxy)\text F \text F \twoheadrightarrow_{\beta} \lambda uv.\text F\text F\text Fvu \twoheadrightarrow_{\beta} \lambda uv.\text F vu \twoheadrightarrow_{\beta} \text T = (1)^*.
$$
Мы получили таблицу истинности функции $f$. $\quad\square$

---

![picture01](/Users/cdraugr-/Desktop/HSE/MathStructs/ComputabilityComplexity/HomeAssignment3/picture01.jpg)

---