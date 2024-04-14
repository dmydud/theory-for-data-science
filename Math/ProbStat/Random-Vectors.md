# Random Vectors

A **random vector** is an ordinary vector with random variables as its entries. So if you have $X$ and $Y$ random variables, then simply the ordered collection $(X, Y)$ is a random vector.

Just like individual random variables have probability density functions or mass functions that govern their probabilistic behavior, random vectors have joint densities, joint mass functions, and joint distribution functions that govern their probabilistic behavior.

Joint density $f(x, y)$ satisfies $f > 0$ and $\displaystyle\iint f(x, y) \, dx \, dy = 1$.

For discrete random variables, $\sum\sum f(x, y) = 1$.

**Note:** In this section, we focus on independent random variables where $f(x, y) = f(x) \cdot g(y)$.

Two events $A$ and $B$ are independent if:

$$P(A \cap B) = P(A) \cdot P(B)$$

Two random variables, $X$ and $Y$, are independent if for any two sets $A$ and $B$:

$$P([X \in A] \cap [Y \in B]) = P(X \in A) \cdot P(Y \in B)$$

If $A$ is independent of $B$, then:

- $A^c$ is independent of $B$;
- $A$ is independent of $B^c$;
- $A^c$ is independent of $B^c$.

If a collection of random variables $X_1, X_2, \ldots, X_n$ are independent, then their joint distribution is the product of their individual densities or mass functions:

$$f(x_1, \ldots, x_n) = \prod_{i=1}^n f_i(x_i)$$

In the instance where $f_1 = f_2 = \ldots = f_n$, we say that the $X_i$ are **independent and identically distributed** (IID).