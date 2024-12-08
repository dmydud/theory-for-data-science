# **00. A Vision of Linear Algebra**

## Fundamental Problem: Solving Systems of Linear Equations

$$
\begin{cases} 
2x - y = 0 \\\ -x + 2y = 3 
\end{cases} \tag{1.1}
$$

## Matrix Form

This system can be written in **matrix form**:

$$
\begin{bmatrix} 
2 \& -1 \\\ -1 \& 2 
\end{bmatrix} 
\begin{bmatrix} 
x \\\
y 
\end{bmatrix} = \begin{bmatrix} 
0 \\\
3 
\end{bmatrix} \tag{1.2}
$$

In shorthand notation:

$$
A\mathbf{x} = \mathbf{b} \tag{1.3}
$$

Here:
- $A$ is the **coefficient matrix**.
- $\mathbf{x}$ is the **unknown vector**.
- $\mathbf{b}$ is the **column vector of constants**.

> **Insight**: $A\mathbf{x}$ represents a **linear combination of the columns of $A$**.

https://github.com/user-attachments/assets/31126bcc-321e-4a89-b097-9a3177443390

## Column Perspective

The same system can be represented as a combination of the columns of $A$:

$$x \begin{bmatrix} 2 \\\ -1 \end{bmatrix} + y \begin{bmatrix} -1 \\\ 2 \end{bmatrix} = \begin{bmatrix} 0 \\\ 3 \end{bmatrix} \tag{1.4}$$

This illustrates the geometric interpretation: the system seeks coefficients $x$ and $y$ that linearly combine the columns of $A$ to produce $\mathbf{b}$.

https://github.com/user-attachments/assets/ce528516-ef76-4c95-851b-78e8211ebbc5

## Column Space $C(A)$

The **column space** of $A$, denoted $C(A)$, is the set of all vectors that can be expressed as $A\mathbf{x}$. Formally:

$$C(A) = \\{ \mathbf{b} \in \mathbb{R}^m \mid \mathbf{b} = A\mathbf{x}, \mathbf{x} \in \mathbb{R}^n \\}.$$

This means $C(A)$ is the subspace spanned by the columns of $A$.

## Row Space $R(A)$

The **row space** of $A$, denoted $R(A)$, is the set of all linear combinations of the rows of $A$. Formally:

$$R(A) = \\{ \mathbf{y} \in \mathbb{R}^n \mid \mathbf{y} = \sum_{i=1}^m c_i \mathbf{r}_i, c_i \in \mathbb{R} \\},$$

where $\mathbf{r}_i$ are the rows of $A$.

## Rank Theorem

The **rank** of a matrix $A$, denoted $\text{Rank}(A)$, is the dimension of both the row and column spaces:

$$
\text{Rank}(A) = r = \dim(C(A)) = \dim(R(A)).
$$

This fundamental equality holds for any matrix.

---

### Example

Given:

$$
A = \begin{bmatrix} 
1 \& 4 \& 5 \\\
3 \& 2 \& 5 \\\
2 \& 1 \& 3 
\end{bmatrix},
$$

the product $A\mathbf{x}$ is:

$$
A\mathbf{x} = 
\begin{bmatrix} 
1 \\\
3 \\\
2 
\end{bmatrix} x_1 
+ 
\begin{bmatrix} 
4 \\\
2 \\\
1 
\end{bmatrix} x_2 
+ 
\begin{bmatrix} 
5 \\\
5 \\\
3 
\end{bmatrix} x_3. 
$$

$$
\begin{bmatrix} 
5 \\\
5 \\\
3 
\end{bmatrix} x_3 = 
\begin{bmatrix} 
1 \\\
3 \\\
2 
\end{bmatrix} x_1 
+ 
\begin{bmatrix} 
4 \\\
2 \\\
1 
\end{bmatrix} x_2 \Rightarrow x_3 = x_1 + x_2$$

### Matrix Factorization $A = CR$

The matrix $A$ can be factorized as:

$$
A = 
\begin{bmatrix} 
1 \& 4 \\\
3 \& 2 \\\
2 \& 2 
\end{bmatrix} 
\begin{bmatrix} 
1 \& 0 \& 1 \\\
0 \& 1 \& 1 
\end{bmatrix},
$$

where $\text{Rank}(A) = r = 2$. The column space $C(A)$ in this example forms a **plane**.

## Basis of Vector Spaces

The **basis** for a vector space consists of the minimum number of linearly independent vectors needed to span the space. For the example above:
- $r = 2$: The basis for the column space consists of two vectors.
- $n - r = 1$: The dependent column is linearly dependent on the other two.

### Counting Theorem

For $A\mathbf{x} = 0$, the number of independent solutions is $n - r$.

## $A = CR$ Factorization: Advantages and Disadvantages

### Advantages
1. $C$: Columns are taken directly from $A$, making the factorization intuitive.
2. $R$: Represents the row-reduced echelon form.
3. Clearly demonstrates $\text{Rank}(A) = r$, with:
   - $C$: Basis for column space.
   - $R$: Basis for row space.

### Disadvantages
1. $C$ and $R$ can be ill-conditioned for certain matrices.
2. For invertible matrices ($A$), $C = A$ and $R = I$, which provides no significant simplification.

