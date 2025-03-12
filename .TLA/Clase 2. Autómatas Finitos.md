> [!NOTE]
>
> ### Autómatas Finitos $A=\langle Q,\Sigma,q_0,F,\delta\rangle$
>
> - $Q$ = Conjunto de estados
> - $\Sigma$ = Conjunto de símbolos terminales
> - $q_0\in Q$= = Estado inicial del autómata
> - $F\subseteq Q$ = Conjunto de estados finales
> - $\delta$ = Función de transición
>   - Se define de $Q\times\Sigma\cup\lbrace\lambda\rbrace\rightarrow P(Q)$

> [!NOTE]
>
> ### Autómatas Finitos Determinísticos (AFD)
>
> #### Función de Transición $\delta$
>
> $$\delta: Q\times\Sigma\rightarrow Q$$
>
> #### Función de Transición Extendida $\hat\delta$
>
> $$\hat\delta: Q\times\Sigma^* \rightarrow Q$$

> [!TIP]
>
> ### Definición sobre la longitud de la cadena de entrada
>
> $\text{Base)}\quad\hat\delta(q,\lambda)=q$
>
> $\text{P.I.)}\quad\text{Si }\omega=\omega'a\quad\Rightarrow\hat\delta(q,\omega)=\delta\bigg(\hat\delta(q,\omega'),a\bigg)$

---

> [!NOTE]
>
> ### Configuración Instantánea
>
> La **configuración instantánea** es una descripción del autómata finito en un momento dado
>
> Se denota con un par $[q,\omega]$, donde $q\in Q\wedge\omega\in\Sigma^*$
>
> El simbolo $\mapsto$ indica el movimiento válido entre dos configuraciones, es decir
>
> $$[q,a\omega]\mapsto[p\omega]\Leftrightarrow\delta(q,a)=p$$

> [!TIP]
>
> ### Secuencia de Configuraciones
>
> $\text{Base)}$ Si $I$ es la configuración instantánea, $I\mapsto *I$
>
> $\text{P.I.)}$ $I\mapsto *J$ es una secuencia válida si existe alguna configuración $K$ tal que $I\mapsto K\wedge K\mapsto *J$

> [!NOTE]
>
> ### Lenguaje aceptado por un autómata finito
>
> #### Mediante secuencia de configuraciones
>
> $$L=\bigg\lbrace\omega\in\Sigma^* \bigg| [q_0,\omega]\mapsto *[p,\lambda],\quad p\in F\bigg\rbrace$$
>
> #### Mediante función de transición extendida
>
> $$L=\bigg\lbrace\omega\in\Sigma^* \bigg| \hat\delta(q_0,\omega)\in F\bigg\rbrace$$

> [!TIP]
>
> ### Equivalencia de autómatas
>
> Sean dos **AFD** $M$ y $M'$
>
> $$M\equiv M'\Leftrightarrow L(M)=L(M' )$$
>
> #### Observaciones
>
> - Si una palabra es reconocida en uno y en otro no, $M\not\equiv M'$
> - La minimización entre dos autómatas equivalentes es única

> [!TIP]
>
> ### Minimización de AFD
>
> 1. Eliminar estados inaccesibles desde $q_0$
> 2. Construir el conjunto de clases de equivalencia de estados

> [!NOTE]
>
> ### Estados Accesibles
>
> - Un estado $q_i\in Q$ es accesible si: $\exists\alpha\in\Sigma^*\bigg|\hat\delta(q_0,\alpha)=q_i\in Q$
> - Un estado $q_i\in Q$ es accesible si: $\exists\alpha\in\Sigma^*\bigg|[q_0,\alpha]\rightarrow[q_i,\lambda]$