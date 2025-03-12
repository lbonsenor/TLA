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
> $$\text{Base)}\quad\hat\delta(q,\lambda)=q$$
>
> $$\text{P.I.)}\quad\text{Si }\omega=\omega'a\quad\Rightarrow\hat\delta(q,\omega)=\delta\bigg(\hat\delta(q,\omega'),a\bigg)$$

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
> $\text{P.I.)}$ $I\mapsto *J$ es una secuencia válida si existe alguna configuración $K$ tal que
>
> $$I\mapsto K\wedge K\mapsto *J$$

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
> ### Equivalencia de autómatas $M\equiv M'$
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

---

> [!NOTE]
>
> ### Estados Accesibles
>
> Un estado $q_i\in Q$ es accesible si:
>
> $$\exists\alpha\in\Sigma^*\bigg|\hat{\delta}(q_0,\alpha)=q_i\in Q$$
>
> $$\exists\alpha\in\Sigma^*\bigg|[q_0,\alpha]\rightarrow[q_i,\lambda]$$

> [!TIP]
>
> ### Construcción Inductiva
>
> $\text{Base)}$ El conjunto de un solo momento $Q'=\lbrace q_0\rbrace$ es accecible ya que
>
> $$\exists\lambda\in\Sigma^*\bigg|\hat\delta(q_0,\lambda)=q_0\in Q$$
>
> $\text{P.I)}$ Si $S\subseteq Q$ es un conjunto de estados accesibles $\forall a\in\Sigma\wedge q_i\in S$, $S'$ es de estados accesibles tal que
>
> $$S'=\bigg\lbrace q_j\in Q\bigg|\delta(q_i,a)=q_j\bigg\rbrace$$

> [!NOTE]
>
> ### Estados equivalentes o Indistinguibles
>
> Los estados $p$ y $q$ son **indistinguibles** si
>
> $$\forall\omega\in\Sigma^*:\hat\delta(p,\omega)\in F\Leftrightarrow\hat\delta(q,\omega)\in F$$
>
> Los estados $p$ y $q$ son **distinguibles** si
>
> $$\exists\omega\in\Sigma^*:\hat\delta(p,\omega)\in F\wedge\hat\delta(q,\omega)\notin F\text\qquad\text{o viceversa}$$
>
> > **Propiedad:** La relación de **indistiguibilidad** es de una relación de **equivalencia**

> [!TIP]
>
> ### Indistiguibilidad de orden $k$ $E_k$
>
> Considera palabras de una misma longitud $k$
>
> - La **indistiguibilidad** de orden $k$ $E_k$ es una relacion de equivalencia
> - Determina una partición del conjunto $Q$ en clases de equivalencia
>
> ---
>
> #### $\text{Lema 1:}$ Dado un autómata, se cumple que $\frac Q {E_0}=\lbrace F, Q-F\rbrace$
>
> $$pE_0q:\quad\forall\omega\in\Sigma^*\wedge|\omega|=0:\hat\delta(p,\lambda)\in F\Leftrightarrow(q,\lambda)\in F$$
>
> $$\text{Por definicion de }\hat\delta:\hat\delta(p,\lambda)=p\wedge\hat\delta(q,\lambda)=q$$
>
> $$\text{Por lo tanto:}\qquad pE_0q\Leftrightarrow\bigg(p\in F\Leftrightarrow q\in F\bigg)$$
>
> ---
>
> #### $\text{Lema 2:}$ Dado un autómata y dos estados $p$ y $q$
>
> $$pE_{n+1}q\Leftrightarrow\forall a\in \Sigma:\delta(p,a)E_n\delta(q,a)$$
>
> Si $\forall a\in\Sigma:\delta(p,a)E_n\delta(q,a)$, eso significa que:
>
> $$\forall\omega\in\Sigma^*\wedge|\omega|=n:\hat\delta(r,\omega)\in F\Leftrightarrow\hat\delta(s,\omega)\in F\text{, siendo }\delta(p,a)=r\wedge\delta(q,a)=s$$
>
> $$\text{Por lo tanto:}\quad\forall\omega'\in\Sigma^*\wedge\omega'=a\omega,|\omega´|=n+1:\hat\delta(p,\omega')\in F\Leftrightarrow(q,\omega')\in F$$

---

> [!TIP]
>
> ### Construcción del conjunto cociente $\frac QE$
>
> `Entrada:` $Q$
>
> `Salida:` Conjunto cociente de $Q$ por la relacion de indistiguibilidad $\frac QE$
>
> 1. $\frac Q{E_0}=\lbrace F, Q-F\rbrace$
> 2. Generar $\frac Q{E_{i+1}}$ a partir de $\frac Q{E_i}$ de la siguiente manera:
>       - Los estados $p$ y $q$ pertenecen a la misma clase en $\frac{Q}{E_{i+1}}\Leftrightarrow$
>           - $p$ y $q$ pertenecen a la misma clase en $\frac Q{E_i}$ y
>           - $\forall a\in\Sigma:\delta(p,a),\delta(q,a)$ pertenecen a la misma clase en $\frac Q{E_i}$
> 3. Si $\frac Q{E_{i+1}}=\frac Q{E_i}$, entonces $\frac Q{E_{i+1}}=\frac Q{E}$. Sino, volver al paso `2`

> [!TIP]
>
> ### Minimización de AFD 2
>
> `Entrada`: $A=\langle Q,\Sigma,\delta,q_0,F\rangle$
>
> `Salida`: $A'=\langle Q',\Sigma,\delta',q_0',F'\rangle$ equivalente a $A$ con mínima cantidad de estados
>
> 1. Eliminar estados accesibles desde $q_0$
> 2. Construir el conjunto cociente $\frac QE$
> 3. $A'=\langle Q',\Sigma,\delta',q_0',F'\rangle$ donde:
>
> $$\begin{cases}
Q'=\frac QE\\
q'_0\text{ es el elemento de }Q'\text{ tal que }q_0\in q'_0\\
F'=\lbrace s\in Q'\wedge S\cap F\ne\oslash\\
\delta'(s_i,a)=s_j\Leftrightarrow\exists p\in s_i\wedge\exists q\in s_j\bigg|\delta(p,a)=q
\end{cases}$$
>
> #### Teorema
>
> El autómata $A’$ obtenido es equivalente al autómata A y es mínimo (el número de estados de $A’$ es menor o igual que el de cualquier otro AFD equivalente a $A$)
