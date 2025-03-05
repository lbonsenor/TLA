>[!NOTE] 
> ### Alfabeto $\Sigma$
>  
> Conjunto no vacio finito de simbolos

> [!IMPORTANT] 
> #### EJ | Alfabeto binario
> $\Sigma=\{0,1\}$

> [!IMPORTANT] 
> #### EJ | Alfabeto de letras minusculas
> $\Sigma=\{a,b,...,z\}$

> [!TIP]  
> ### Potencias de un Alfabeto $\Sigma^𝑘$
> 
> Es el conjunto de cadenas de una determinada longitud sobre el alfabeto tal que $\forall\omega\in\Sigma: |\omega|=k$

---

> [!NOTE] 
> ### Cadena $\omega$
> 
> Secuencia finita de símbolos seleccionados de algún alfabeto.
> - **Longitud de una cadena** $|\omega|$: cantidad de símbolos
> - **Cadena vacia**: $\lambda$
 
> [!TIP]
> ### Concatenacion de cadenas $x.y$
>
> #### Propiedades
> - **Cerrada**: la concatenación de cadenas es una cadena.
> - **Asociativa**: $\forall x,y,z: (x.y).z=x.(y.z)$
> - **Elemento neutro**: la palabra vacía $\lambda$

> [!NOTE] 
> ### Cadena: Definicion recursiva 
> - $\lambda$ es una cadena
> - Si a es un simbolo $(a\in\Sigma)$ y $\omega$ es una cadena, entonces $a.\omega$ es una cadena

> [!TIP]
> ### Reversion de una cadena
> Definicion recursiva:
> - $\lambda^r = \lambda$
> - $(a\omega)^r=(\omega)^ra$

---

> [!NOTE] 
> ### Lenguaje $L$
> 
> Dado un $\Sigma$, un lenguaje $L$ es un subconjunto de $\Sigma^*$ tal que $L\subseteq\Sigma^*$

> [!TIP] 
> - **Union**: $L_1\cup L_2$
> - **Clausura**: $L_1^* = \{\lambda,ab,ac,ad,abab,abac,abad,acab,...\}$
> - **Reversa**: $L_1^r = \{ba,ca,da\}$
> - **Producto**: $L_1\cdot L_2 = \{w\ |\ w=xy, x\in L_1\wedge y\in L_2\}$
> - **Potencia**: $L^i=L\cdot L...\cdot L$ ($i$ veces)
> - **Clausura**: $L^+=\bigcup^\infty_{i=1}L^i$
> - **Clausura de Keene:**: $L^*=\bigcup^\infty_{i=0}L^i$

> [!NOTE]  
> ### Inducción Estructural
> 
> **Las definiciones recursivas tienen:**  
> - Un caso base, en el que se definen una o más estructuras elementales,  
> - Un paso de inducción, en el que se definen estructuras más complejas en  términos de estructuras previamente definidas.
> 
> Cuando tenemos una definición recursiva, se pueden probar teoremas acerca de ella utilizando **inducción estructural**. 
>  
> Sea $P(X)$ una proposición acerca de estructuras $X$ definidas mediante alguna definición  
recursiva determinada.  
> 1. Como base se prueba $P(x)$ para $x = \text{caso base de la definición}$.  
> 2. Para el paso de inducción se toma una estructura $X$ que está formada a partir de  
$Y1,Y2,..Yk$, se dan por ciertas $P(Y1), P(Y2), …., P(Yk)$ y se usan para demostrar $P(X)$

> [!IMPORTANT] 
> #### EJ | Arbol
> 
> **Base:** Un nodo es un arbol
> 
> **Paso inductivo**: Si $T_1. T_2, ..., T_k$ son árboles, se puede construir un nuevo árbol de la siguiente manera
> 1. Se comienza con un nuevo nodo $(N)$, que es la raíz del arbol
> 2. Se añaden arcos desde el nodo $N$ hasta las raíces de cada uno de los árboles
> 
> **Propiedad**: Si $T$ es un árbol y tiene $n$ nodos, entonces tiene $n-1$ arcos

---

> [!NOTE] 
> ### Definición Grámaticas $\langle N,\Sigma,S,P\rangle$ o $\langle V,\Sigma,S,P\rangle$
>  
> Una **gramática** es un sistema matemático para definir un lenguaje
> - $N$= conjunto de símbolos no terminales
> - $\Sigma$= conjunto de símbolos terminales $N\cap\Sigma=\oslash$
> - $S$ = símbolo inicial de la gramática
> - $P$ = conjunto de producciones $\alpha\rightarrow\beta$ donde $\alpha\in (N\cup\Sigma)^+\wedge\beta\in (N\cup\Sigma)^*$ 

---

> [!NOTE]
> ### Formas Sentenciales
>  
> **CB**: $S\text{ es una forma sentencial}$
> 
> **P.I.**: $\text{Si } \alpha\beta\gamma\text{ es una }f.s\wedge\beta\rightarrow\delta\in P\Rightarrow\alpha\delta\gamma\text{ es una forma sentencial}$
 
---

> [!NOTE] 
> ### Clasificación de gramáticas según Chomsky
>
> #### Tipo 0: Irrestrictas
> Producciones $\alpha\rightarrow\beta$ donde $\alpha\in(N\cup\Sigma)^+\wedge\beta\in(N]cup\Sigma)^*$
>
> #### Tipo 1: Sensibles al contexto
> Producciones $\alpha\rightarrow\beta$ donde $|a|\ge|\beta|\ (\text{salvo } S\rightarrow\lambda)$
>
> #### Tipo 2: Libres de contexto
> Producciones $A\rightarrow\beta$ donde $A\in N$
>
> #### Tipo 3: Regulares
> Producciones de alguna de las siguientes formas
> $\begin{cases}A\rightarrow bC\\ A\rightarrow b\\ A\rightarrow\lambda\end{cases}\qquad\vee\qquad \begin{cases}A\rightarrow Cb\\ A\rightarrow b\\ A\rightarrow \lambda\end{cases}$

---
