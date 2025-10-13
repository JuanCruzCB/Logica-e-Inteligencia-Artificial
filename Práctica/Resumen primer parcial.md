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

## Demostración sintáctica

---

# Capítulo 3 Hamilton (Prácticas 4 y 5)

## Representación simbólica LO1

## Equivalencia entre $\forall $ y $\exists $

## Variables ligadas vs libres

## Fórmulas contradictorias, satisfactibles, verdaderas, lógicamente válidas

---

# Capítulo 4 Hamilton (Práctica 6)

## Lógica de Hoare
