# Capítulo 1 Hamilton (Prácticas 1 y 2)

## Conceptos básicos

- **Conectiva**: no, y, o, si entonces, si y solo si.
- **Frase simple**: Oración que consta de un sujeto y un predicado.
- **Frase compuesta**: Oración que consta de dos o más frases simples unidas por conectores lógicos.

Una frase puede no ser ni verdadera ni falsa.

- **Enunciado simple o compuesto**: igual que una frase simple o compuesta, pero siempre es verdadero o falso. Se denotan con letras mayúsculas $(A, B, C, ...)$.

## Tablas de verdad básicas

### Negación ($\lnot$)

| $p$ | $\lnot p$ |
| --- | --------- |
| V   | F         |
| F   | V         |

### Conjunción ($\land$)

- Es conmutativa: (p $\land$ q) $\Leftrightarrow$ (q $\land$ p)
- Es asociativa: ((p $\land$ q) $\land$ r) $\Leftrightarrow$ (p $\land$ (q $\land$ r))
- Es distributiva respecto a la disyunción: (p $\land$ (q $\lor$ r)) $\Leftrightarrow$ ((p $\land$ q) $\lor$ (p $\land$ r))

| $p$ | $q$ | $p \land q$ |
| --- | --- | ----------- |
| V   | V   | V           |
| V   | F   | F           |
| F   | V   | F           |
| F   | F   | F           |

### Disyunción ($\lor$)

- Es conmutativa: (p $\lor$ q) $\Leftrightarrow$ (q $\lor$ p)
- Es asociativa: ((p $\lor$ q) $\lor$ r) $\Leftrightarrow$ (p $\lor$ (q $\lor$ r))
- Es distributiva respecto a la conjunción: (p $\lor$ (q $\land$ r)) $\Leftrightarrow$ ((p $\lor$ q) $\land$ (p $\lor$ r))

| $p$ | $q$ | $p \lor q$ |
| --- | --- | ---------- |
| V   | V   | V          |
| V   | F   | V          |
| F   | V   | V          |
| F   | F   | F          |

### Condicional ($\rightarrow$)

| $p$ | $q$ | $p \rightarrow q$ |
| --- | --- | ----------------- |
| V   | V   | V                 |
| V   | F   | F                 |
| F   | V   | V                 |
| F   | F   | V                 |

### Bicondicional ($\leftrightarrow $)

| $p$ | $q$ | $p \leftrightarrow q$ |
| --- | --- | --------------------- |
| V   | V   | V                     |
| V   | F   | F                     |
| F   | V   | F                     |
| F   | F   | V                     |

## Forma enunciativa

Una forma enunciativa (f.e) es una expresión en la cual intervienen variables de enunciado (p, q, r, ...) y conectivos lógicos, que pueda formarse utilizando las reglas:

- Toda variable de enunciado es una f.e.
- Si A y B son f.e., entonces ($\lnot A$), ($A \land B$), ($A \lor B$), ($A \rightarrow B$) y ($A \leftrightarrow B$) son f.e.

## Tablas de verdad en general

- Si una f.e tiene $n$ variables de enunciado, su tabla de verdad tendrá $2^n$ filas.

## Tautología, contradicción y contingencia

Para saber si una f.e es tautología, contradicción o contingencia, se construye su tabla de verdad y se observa la columna final.

### Tautología

- **Tautología**: f.e que toma el valor de verdad $V$ bajo cada una de las posibles asignaciones de valores de verdad a sus variables de enunciado.
- Ejemplo: $(p \lor \lnot p)$

| $p$ | $\lnot p$ | $p \lor \lnot p$ |
| --- | --------- | ---------------- |
| V   | F         | V                |
| F   | V         | V                |

### Contradicción

- **Contradicción**: f.e que toma el valor de verdad $F$ bajo cada una de las posibles asignaciones de valores de verdad a sus variables de enunciado.
- Ejemplo: $(p \land \lnot p)$

| $p$ | $\lnot p$ | $p \land \lnot p$ |
| --- | --------- | ----------------- |
| V   | F         | F                 |
| F   | V         | F                 |

### Contingencia

- **Contingencia**: f.e que no es ni tautología ni contradicción.
- Ejemplo: $(p \land q)$

| $p$ | $q$ | $p \land q$ |
| --- | --- | ----------- |
| V   | V   | V           |
| V   | F   | F           |
| F   | V   | F           |
| F   | F   | F           |

## Implicación lógica y equivalencia lógica

- Sean $A$ y $B$ dos f.e.
- $A$ **implica lógicamente** a $B$ si $(A \rightarrow B)$ es una tautología.
  - Se denota $(A \Rightarrow B)$
- $A$ y $B$ son **lógicamente equivalentes** si $(A \leftrightarrow B)$ es una tautología.
  - Se denota $(A \Leftrightarrow B)$
  - Ejemplo: $(p \land p) \Leftrightarrow p$

## Leyes de De Morgan

- Sean $A$ y $B$ dos f.e.
- $\lnot (A \land B) \Leftrightarrow (\lnot A \lor \lnot B)$
- $\lnot (A \lor B) \Leftrightarrow (\lnot A \land \lnot B)$

## Formas normales

### Forma normal disyuntiva (FND)

- Toda f.e que **no sea una contradicción** es lógicamente equivalente a una f.e restringida de la forma: $$(\bigvee_{i=1}^{m} (\bigwedge_{j=1}^{n} Q_{ij}))$$ siendo $Q_{ij}$ una variable de enunciado o la negación de una variable de enunciado.

### Forma normal conjuntiva (FNC)

- Toda f.e que **no sea una tautología** es lógicamente equivalente a una f.e restringida de la forma: $$(\bigwedge_{i=1}^{m} (\bigvee_{j=1}^{n} Q_{ij}))$$ siendo $Q_{ij}$ una variable de enunciado o la negación de una variable de enunciado.

## Conjuntos adecuados de conectivas

- Un conjunto de conectivas es adecuado si toda función de verdad puede representarse mediante una f.e que utilice únicamente conectivas de dicho conjunto.
- Ejemplos de conjuntos adecuados:
  - $\{\lnot, \land, \lor \}$
  - $\{\lnot, \land\}$
  - $\{\lnot, \lor\}$
  - $\{\lnot, \rightarrow\}$
  - $\{\uparrow\}$ (NAND)
  - $\{\downarrow\}$ (NOR)

## Formas argumentativas

### Definición

- Una forma argumentativa (f.a) es una sucesión finita de formas enunciativas llamadas **premisas**, y una forma enunciativa llamada **conclusión**:

$$ A_1, A_2, \ldots, A_n \therefore A $$

donde $A_1, A_2, \ldots, A_n$ son las **premisas** y $A$ es la **conclusión**.

### Validez e invalidez

#### Definición e implicaciones

- Una f.a es es **inválida** si es posible que todas las premisas sean verdaderas y la conclusión falsa a la vez. En cualquier otro caso, la f.a es **válida**.
- ¿Qué ocurre con la conclusión?
  - Si la f.a es válida y las premisas son verdaderas, la conclusión es verdadera.
  - Si la f.a es válida y alguna premisa es falsa, no se puede determinar si la conclusión es verdadera o falsa.
  - Si la f.a es inválida, no se puede determinar si la conclusión es verdadera o falsa.

#### Método 1 para determinar validez o invalidez (tabla de verdad)

- Se construye la tabla de verdad con todas las formas enunciativas de la f.a, tanto las premisas como la conclusión.
- Ejemplo de f.a inválida con 2 premisas:

  - Premisas: $p$, $p \rightarrow q$
  - Conclusión: $\lnot q$
  - Tabla de verdad:

  | $p$ | $q$ | $p \rightarrow q$ | $\lnot q$ |
  | --- | --- | ----------------- | --------- |
  | V   | V   | V                 | F         |
  | V   | F   | F                 | V         |
  | F   | V   | V                 | F         |
  | F   | F   | V                 | V         |

  - En la primer fila, ambas premisas son verdaderas y la conclusión es falsa, por lo que la f.a es inválida.

#### Método 2 para determinar validez o invalidez (método sencillo)

- Método sencillo para determinar si una f.a es inválida sin necesidad de construir la tabla de verdad completa:
  - Se fuerza la conclusión a ser falsa.
  - Se fuerza cada premisa a ser verdadera.
  - Se chequea si existe alguna combinación de valores de verdad para las variables de enunciado que cumpla lo anterior.
  - Ejemplo:
    - Premisas: $p$, $p \rightarrow q$
    - Conclusión: $\lnot q$
    - Paso 1: $\lnot q$ debe ser F, por lo tanto $q$ debe ser V.
    - Paso 2: $p$ debe ser V.
    - Paso 3: $p \rightarrow q$ debe ser V. Como $p$ es V y $q$ es V, $p \rightarrow q$ es V.
    - Paso 4: Existe una combinación de valores de verdad que hace que la conclusión sea F pero las premisas V: $p$ es V y $q$ es V. Por lo tanto, la f.a es inválida.

#### Método 3 para determinar validez o invalidez (proposición 1.32)

- Sea $A_1, A_2, \ldots, A_n \therefore A$ una forma argumentativa.
- La f.a es válida si y sólo si la f.e $((A_1 \land A_2 \land \ldots \land A_n) \rightarrow A)$ es una **tautología**.
- Ejemplo:

  - Premisas: $p$, $p \rightarrow q$
  - Conclusión: $\lnot q$
  - Forma enunciativa a analizar: $(p \land (p \rightarrow q)) \rightarrow \lnot q$
  - Tabla de verdad:

  | $p$ | $q$ | $p \rightarrow q$ | $p \land (p \rightarrow q)$ | $\lnot q$ | $(p \land (p \rightarrow q)) \rightarrow \lnot q$ |
  | --- | --- | ----------------- | --------------------------- | --------- | ------------------------------------------------- |
  | V   | V   | V                 | V                           | F         | F                                                 |
  | V   | F   | F                 | F                           | V         | V                                                 |
  | F   | V   | V                 | F                           | F         | V                                                 |
  | F   | F   | V                 | F                           | V         | V                                                 |

  - La f.e no es una tautología, por lo que la f.a es inválida.

---

# Capítulo 2 Hamilton (Práctica 3)

## Definición del sistema formal $L$

- El sistema formal $L$ del cálculo de enunciados se define mediante 4 componentes:

1. **Alfabeto infinito de símbolos**:
   - Variables de enunciado: $p_1, p_2, p_3, ...$
   - Conectivas lógicas: $\lnot, \rightarrow$
   - Paréntesis: $(, )$
2. **Conjunto de fbfs**:
   - $p_i$ es una fbf $\forall i \ge 1$
   - Si $A$ y $B$ son fbfs, entonces $(\lnot A)$ y $(A \rightarrow B)$ son fbfs.
3. **Esquemas de axiomas ($A, B, C$ son cualquier fbf)**:
   - $L1$: $(A \rightarrow (B \rightarrow A))$
   - $L2$: $((A \rightarrow (B \rightarrow C)) \rightarrow ((A \rightarrow B) \rightarrow (A \rightarrow C)))$
   - $L3$: $((\lnot A \rightarrow (\lnot B)) \rightarrow (B \rightarrow A))$
4. **Reglas de inferencia o deducción**: En $L$ solo se tiene una regla llamada Modus Ponens (MP).

   - Sean $A$ y $B$ dos fbfs arbitrarias.
   - De $A$ y $A \rightarrow B$ se deduce como consecuencia directa $B$.

## Demostración en $L$

- Una demostración en $L$ es una secuencia finita de fbfs $A_1, A_2, \ldots, A_n$ donde cada $A_i$ es un **axioma** (una instancia de $L1$, $L2$ o $L3$), o se **deduce por MP** de dos fbfs anteriores en la secuencia.
- Una tal demostración se dice que es una demostración de $A_n$ en $L$.
- También se dice que $A_n$ es un **teorema** de $L$.

## Deducción a partir de Gamma ($\Gamma$)

- Sea $\Gamma$ un conjunto de fbfs de $L$, ya sean axiomas o teoremas o no.
- Una sucesión finita $A_1, A_2, \ldots, A_n$ de fbfs de $L$ es una **deducción a partir de $\Gamma$** si para todo i $(1 \le i \le n)$ se cumple alguna de las condiciones:
  - $A_i$ es un **axioma** de $L$.
  - $A_i \in \Gamma$.
  - $A_i$ se deduce por MP de dos fbfs anteriores en la secuencia.
- Intuitivamente, una deducción a partir de $\Gamma$ es una **demostración** en $L$ en la que los miembros de $\Gamma$ se consideran temporalmente como axiomas.
- El último elemento $A_n$ de una deducción a partir de $\Gamma$ se dice que es deducible a partir de $\Gamma$, o que es una consecuencia directa de $\Gamma$ en $L$.
- Si una fbf $A$ es el último miembro de una deducción a partir de $\Gamma$, se escribe $\Gamma \vdash_L A$ y se dice que $A$ es derivable a partir de $\Gamma$ en $L$.
- Todo teorema de $L$ es deducible a partir del conjunto vacío de fbfs, de forma que si $A$ es un teorema de $L$, entonces $\emptyset \vdash_L A$ o abreviadamente $\vdash_L A$.
- Ejemplo:
  - $\Gamma$ = $\{A, (B \rightarrow (A \rightarrow C))\}$
  - (1): $A$ (Hipótesis)
  - (2): $(B \rightarrow (A \rightarrow C))$ (Hipótesis)
  - (3): $(A \rightarrow (B \rightarrow A))$ (Instanciación de $L1$)
  - (4): $(B \rightarrow A)$ (MP entre (1) y (3))
  - (5): $((B \rightarrow (A \rightarrow C)) \rightarrow ((B \rightarrow A) \rightarrow (B \rightarrow C)))$ (Instanciación de $L2$)
  - (6): $((B \rightarrow A) \rightarrow (B \rightarrow C))$ (MP entre (2) y (5))
  - (7): $(B \rightarrow C)$ (MP entre (4) y (6))
  - Por lo tanto, para fbfs $A, B, C$ cualesquiera: $$\{A, (B \rightarrow (A \rightarrow C))\} \vdash_L (B \rightarrow C)$$

## Metateorema de la deducción (MTD)

- Sea $\Gamma$ un conjunto de fbfs de $L$ potencialmente vacío y sean $A$ y $B$ dos fbfs cualesquiera.
- Si $\Gamma \cup \{A\} \vdash_L B$, entonces $\Gamma \vdash_L (A \rightarrow B)$.
- Este metateorema es recíproco:
- Si $\Gamma \vdash_L (A \rightarrow B)$, entonces $\Gamma \cup \{A\} \vdash_L B$.

## Silogismo hipotético (SH)

- Sean $A, B$ y $C$ tres fbfs cualesquiera.
- Si $\Gamma = \{(A \rightarrow B), (B \rightarrow C)\}$, entonces $\Gamma \vdash_L (A \rightarrow C)$.

## Valoración de $L$

- Una valoración de $L$ es una función $v$ cuyo dominio es el conjunto de todas las fbfs de $L$ y cuyo rango es el conjunto $\{V, F\}$, tal que para toda fbf $A$ y $B$:
  - $v(A) \neq v(\lnot A)$
  - $v(A \rightarrow B) = F$ si y sólo si $v(A) = V$ y $v(B) = F$

## Tautología en $L$

- Una fbf $A$ de $L$ es una **tautología** si para toda valoración $v$ de $L$, $v(A) = V$.
- **Además, $A$ es un teorema si y sólo si $A$ es una tautología. Por lo tanto, todo teorema de $L$ es una tautología**.

## Extensión de $L$

- Una extensión de $L$ es un sistema formal $L'$ que se obtiene de $L$ ampliando o alterando el conjunto de axiomas de manera que todos los teoremas de $L$ sigan siendo teoremas en $L'$.
- Es posible que $L'$ introduzca nuevos teoremas que no son teoremas de $L$.
- Es posible que un sistema formal $L'$ sea una extensión de $L$ sin tener axiomas en común con $L$.
- Si se extiende demasiado un sistema formal, se puede llegar a un sistema en el que cualquier fbf sea un teorema, lo cual es indeseable.

## Consistencia

- **El sistema formal $L$ es consistente**.
- Una extensión $L'$ de $L$ es **consistente** si no existe ninguna fbf $A$ de $L$ tal que tanto $A$ como $\lnot A$ sean teoremas de $L'$.
- Además, una extensión $L'$ de $L$ es consistente si y sólo si existe alguna fbf $A$ de $L$ que no es teorema de $L'$.

## Completitud

- **El sistema formal $L$ no es completo**.
- Una extensión $L'$ de $L$ es **completa** si para toda fbf $A$ de $L$, $A$ o $\lnot A$ es un teorema de $L'$.
- Toda extensión inconsistente de $L$ es completa, pero no toda extensión consistente de $L$ es completa.

## Decidibilidad

- **El sistema formal $L$ es decidible**.
- Un sistema formal es decidible si existe un método efectivo para decidir si cada fbf del sistema es un teorema o no.

## Teorema de adecuación de $L$

- Si $A$ es una fbf de $L$ y $A$ es una tautología, entonces $A$ es un teorema de $L$: $\vdash_L A$.

---

# Capítulo 3 Hamilton (Prácticas 4 y 5)

## Representación simbólica LO1

## Equivalencia entre $\forall $ y $\exists $

## Variables ligadas vs libres

## Fórmulas contradictorias, satisfactibles, verdaderas, lógicamente válidas

---

# Capítulo 4 Hamilton (Práctica 6)

## Lógica de Hoare
