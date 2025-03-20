> [!NOTE]
>
> ### Autómatas Finitos No Determinísticos (AFND) $A=\langle Q,\Sigma,q_0,F,\delta\rangle$
>
> $\delta$: Función de transición y se define de $Q\times\Sigma\rightarrow P(Q)$
>
> $\text{Función de transición extendida: }$
>
> $\text{Base) }$
> $$\hat\delta(q,\lambda)=\lbrace q\rbrace$$
> $\text{P.I) si}$
> $$\omega=\omega'a, \hat\delta(q,\omega')=\lbrace p_1,p_2,\ldots,p_n\rbrace\wedge\bigcup^k_{i=1}\delta(p_i,a)=\lbrace r_1,r_2,\ldots,r_m\rbrace\\
\Rightarrow \hat\delta(q,\omega)=\hat\delta(q,\omega',a)=\lbrace r_1,r_2,\ldots,r_m\rbrace$$

> [!NOTE]
>
> ### Lenguaje aceptado por un AFND
>
> #### Mediante secuencia de configuraciones
>
> $$L=\bigg\lbrace\omega\in\Sigma^\ast \bigg| [q_0,\omega]\mapsto *[p,\lambda],\quad p\in F\bigg\rbrace$$
>
> #### Mediante función de transición extendida
>
> $$L=\bigg\lbrace\omega\in\Sigma^\ast \bigg| \hat\delta(q_0,\omega)\cap F\ne\oslash\bigg\rbrace$$

> [!TIP]
>
> ### Equivalencia entre AFD y AFND
>
> *Todo lenguaje reconocido por un AFND puede ser reconocido por un AFD y viceversa*
>
> #### Construcción de Subconjuntos
>
> Sea $N=\langle Q_N,\Sigma,\delta_N, q_0, F_N\rangle$ un AFND y sea $D=\langle Q_D,\Sigma,\delta_D,\lbrace q_0\rbrace, F_D\rangle$
>
> - $Q_D=P(Q_N)$
> - $F_D=\lbrace S\in Q_D \big| S\cap F_N\ne\oslash\rbrace$
> - $\forall a\in SIgma,\forall S\subseteq Q_N:\delta_D(S,a)=\bigcup_{p\in S}\delta_N(p,a)$
>
> Se puede hacer una "construccion *lazy*" para dejar en $Q_D$ sólo los estados accesibles
>
> 1. $\lbrace q_0\rbrace \in Q_D$
> 2. $\forall a\in\Sigma,\forall S\in Q_D,\text{ si }\delta_D(S,a)\notin Q_D\text{, agrego }\delta_D(S,a)\text{ a }Q_D$
>
> #### Primera parte
>
> $$\text{Si } D=\langle Q_D,\Sigma,\delta_D,\lbrace q_0\rbrace, F_D\rangle\text{ se construyó a partir de }N=\langle Q_N,\Sigma,\delta_N,q_0,F_N\rangle\\
L(D)=L(N)$$
>
> #### Segunda parte
>
> $$\exists N=\langle Q_N,\Sigma,\delta_N,\lbrace q_0\rbrace, F_N\rangle\text{ construido a partir de }\langle Q_D,\Sigma,\delta_D,q_0, F_D\rangle\\
\text{ tal que }L(D)=L(N)$$
