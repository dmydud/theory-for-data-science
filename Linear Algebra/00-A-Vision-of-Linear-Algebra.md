# **00. A Vision of Linear Algebra**

## Fundamental Problem: Solving Systems of Linear Equations

$$
\begin{cases} 
2x - y = 0 \\\\ -x + 2y = 3 
\end{cases} \tag{1.1}
$$

## Matrix Form

This system can be written in **matrix form**:

$$
\begin{bmatrix} 
2 \& -1 \\\\ -1 \& 2 
\end{bmatrix} 
\begin{bmatrix} 
x \\\\
y 
\end{bmatrix} = \begin{bmatrix} 
0 \\\\
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

$$x \begin{bmatrix} 2 \\\\ -1 \end{bmatrix} + y \begin{bmatrix} -1 \\\\ 2 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 3 \end{bmatrix} \tag{1.4}$$

This illustrates the geometric interpretation: the system seeks coefficients $x$ and $y$ that linearly combine the columns of $A$ to produce $\mathbf{b}$.

https://github.com/user-attachments/assets/ce528516-ef76-4c95-851b-78e8211ebbc5

## Column Space $C(A)$

The **column space** of $A$, denoted $C(A)$, is the set of all vectors that can be expressed as $A\mathbf{x}$. Formally:

$$C(A) = \\\{ \mathbf{b} \in \mathbb{R}^m \mid \mathbf{b} = A\mathbf{x}, \mathbf{x} \in \mathbb{R}^n \\\}.$$

This means $C(A)$ is the subspace spanned by the columns of $A$.

## Row Space $R(A)$

The **row space** of $A$, denoted $R(A)$, is the set of all linear combinations of the rows of $A$. Formally:

$$R(A) = \\\{ \mathbf{y} \in \mathbb{R}^n \mid \mathbf{y} = \sum_{i=1}^m c_i \mathbf{r}_i, c_i \in \mathbb{R} \\\},$$

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
1 \& 4 \& 5 \\\\
3 \& 2 \& 5 \\\\
2 \& 1 \& 3 
\end{bmatrix},
$$

the product $A\mathbf{x}$ is:

$$
A\mathbf{x} = 
\begin{bmatrix} 
1 \\\\
3 \\\\
2 
\end{bmatrix} x_1 
+ 
\begin{bmatrix} 
4 \\\\
2 \\\\
1 
\end{bmatrix} x_2 
+ 
\begin{bmatrix} 
5 \\\\
5 \\\\
3 
\end{bmatrix} x_3. 
$$

$$
\begin{bmatrix} 
5 \\\\
5 \\\\
3 
\end{bmatrix} x_3 = 
\begin{bmatrix} 
1 \\\\
3 \\\\
2 
\end{bmatrix} x_1 
+ 
\begin{bmatrix} 
4 \\\\
2 \\\\
1 
\end{bmatrix} x_2 \Rightarrow x_3 = x_1 + x_2$$

### Matrix Factorization $A = CR$

The matrix $A$ can be factorized as:

$$
A = 
\begin{bmatrix} 
1 \& 4 \\\\
3 \& 2 \\\\
2 \& 2 
\end{bmatrix} 
\begin{bmatrix} 
1 \& 0 \& 1 \\\\
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
2. For invertible matrices $A$, $C = A$ and $R = I$, which provides no significant simplification.

## Null Space

When we solve $A\mathbf{x} = 0$, where $A$ is an $m \times n$ matrix, the system can be expressed as:

$$\begin{bmatrix}\text{row } 1 \\\ \dots \\\  \text{row } m\end{bmatrix}\begin{bmatrix}x\end{bmatrix}=\begin{bmatrix}0 \\\ \dots \\\ 0 \end{bmatrix}\tag{1.5}$$

The set of all solutions $\mathbf{x}$ to $A\mathbf{x} = 0$ forms the **null space** of $A$, which is a subspace of $\mathbb{R}^n$.

From Equation (1.5), the nullspace has the following key properties:

- Every vector $\mathbf{x}$ in the nullspace of $A$ is orthogonal to the row space of $A$. This can be expressed as:
$$N(A) \perp C(A^T)$$
where $C(A^T)$ is the column space of $A^T$, which corresponds to the row space of $A$.

- Every vector $\mathbf{y}$ in the null space of $A^T$ is orthogonal to the column space of $A$:

$$N(A^T) \perp C(A)$$

### Example

$$\begin{cases}2x + 3y = 7 \\\ 4x + 7y = 15 \end{cases} \Rightarrow\begin{cases}2x + 3y = 7 \\\ y = 1 \end{cases} \Rightarrow \begin{cases}x = 2 \\\ y = 1 \end{cases}$$

$$A = 
\begin{bmatrix} 2 \& 3 \\\ 4 \& 7 \end{bmatrix} = 
\begin{bmatrix} 1 \& 0 \\\ 2 \& 1 \end{bmatrix}\begin{bmatrix} 2 \& 3 \\\ 0 \& 1 \end{bmatrix} = LU$$

If the rows of $A$ are exchanged, we introduce a **permutation matrix** $P$, and the factorization becomes:

$$PA = LU$$

Here, $P$ reorders the rows to ensure numerical stability during factorization.

## LU Factorisation

The $LU$ factorization decomposes a matrix $A$ into the product of a **lower triangular matrix** $L$ and an **upper triangular matrix** $U$:

$$A = LU$$

### Algorithm for $LU$ Factorisation

Initialise $L$ and $U$: Start with $L$ as the identity matrix and $U$ as $A$.

**Step 1.** Eliminate below the pivot (column 1):
   - Subtract a multiple of row 1 $(l_{i1}$) from each subsequent row $i$ to produce zeros below the pivot in column 1.  
   - Store $l_{i1}$ values in the corresponding entries of $L$.

**Step 2.** Repeat for the reduced matrix $A_2$: 
   - Focus on the submatrix formed by removing the first row and column.  
   - Apply the same elimination process to produce zeros below the pivot in column 2.

**Continue** until all columns are processed: Repeat for $A_3, A_4, \dots$, until reaching the $n$-th column.

**Result:** The matrix $L$ is **lower triangular**, containing the multipliers $l_{ij}$ used for elimination. The matrix $U$ is **upper triangular**, representing the resulting matrix after all row reductions.

$$A = LU = \begin{bmatrix}1 \& 0 \& \dots \& 0 \\\ l_{21} \& 1 \& \dots \& 0 \\\ \dots \& \dots \& \dots \& 0 \\\ l_{n1} \& l_{n2} \& \dots \& 1\end{bmatrix}
\begin{bmatrix}\text{row 1 of }A \\\ \begin{matrix}\begin{matrix} 0 \\\ \\\ 0 \end{matrix} \& \begin{matrix}\text{row 1 of }A_2 \\\ \begin{matrix} \begin{matrix} \\\ 0 \end{matrix} \& \begin{matrix}\cdots \\\ \begin{matrix} 0 \& \text{row 1 of }A_n \end{matrix}\end{matrix}\end{matrix}\end{matrix}\end{matrix} \end{bmatrix}$$

## Orthogonality and Orthonormal Columns

Given two vectors $x$ and $y$, the following holds:

$$x^T y = 0 \quad \text{(i.e., $x$ and $y$ are orthogonal)}$$

$$y^T x = 0 \quad \text{(symmetry of the dot product)}$$

$$(x + y)^T(x + y) = x^T x + y^T y \quad \text{(expanding the square)}$$

### Orthonormal Columns of $Q$

Let $q_1, q_2, \dots, q_n$ be orthonormal columns of a matrix $Q$. These columns are orthogonal unit vectors, meaning:

$$Q^T Q = \begin{bmatrix} — \& q_1^T \& — \\\ \vdots \& \vdots \& \vdots \\\ — \& q_n^T \& — \end{bmatrix} 
\begin{bmatrix} \| \& \& \| \\\ q_1 \& \dots \& q_n \\\ \| \& \& \| \end{bmatrix} = I_n$$

This equation indicates that the matrix $Q^T Q$ is the identity matrix, meaning the columns of $Q$ are **orthonormal**.

This implies that the matrix $Q$ preserves the lengths of vectors. In other words, for any vector $x$, we have:

$${\|\|Qx\|\|}^2=x^TQ^TQx=x^Tx={\|\|x\|\|}^2$$

This means that the length (or norm) of the vector $x$ is preserved after the transformation by $Q$. The matrix $Q$ is said to be **length-preserving**.

For a general matrix $Q$, even if it is not square, we have:

$$QQ^T QQ^T = QQ^T$$

which means that $QQ^T$ is a **projection matrix** (idempotent matrix) onto the column space of $Q$.

If $Q$ is square (i.e., $Q$ is $n \times n$), then the equation $Q^T Q = I_n$ implies that $Q$ is an orthogonal matrix. In this case, the following also holds:

$$QQ^T = I_n$$

Thus, $Q$ is an orthogonal matrix where the transpose is also the inverse:

$$Q^T = Q^{-1}$$

### Eigenvalues of $Q$

For an orthogonal matrix $Q$, the following holds for any vector $x$:

$$Qx = \lambda x$$

This implies that the eigenvalues $\lambda$ of an orthogonal matrix must satisfy:

$${\|\|Qx\|\|}^2 = {\|\lambda\|}^2 {\|\|x\|\|}^2$$

Since $Q$ preserves lengths, we have:

$$\|\|Qx\|\| = \|\|x\|\|$$

Thus, ${\|\lambda\|}^2 = 1$, meaning that the eigenvalues of an orthogonal matrix are $\pm 1$.

## QR Factorization

In linear algebra, a matrix $A$ can be factorized into the product of an orthogonal matrix $Q$ and an upper triangular matrix $R$ using the **QR factorization**:

$$A = QR$$

Here, $Q$ has orthonormal columns, and $R$ is an upper triangular matrix. The relationship between $Q$ and $A$ can be expressed as:

$$Q^T A = R$$

This factorization is often used in solving systems of linear equations and finding eigenvalues.

## Least Squares and its Relation to QR Factorization

In the context of solving **overdetermined systems** (i.e., systems of equations with more equations than unknowns), one of the most common approaches is the **least squares** method. This approach is particularly useful when the system of equations does not have an exact solution but a solution that minimizes the error is desired. QR factorization plays a critical role in efficiently solving the least squares problem.

### The Least Squares Problem

Given a system of linear equations:

$$Ax = b$$

where $A$ is an $m \times n$ matrix with $m \geq n$, the system may be **overdetermined**, meaning there are more equations than unknowns. In many cases, this system does not have an exact solution because $b$ is not exactly in the column space of $A$. Instead, we seek an approximate solution that minimizes the **residual error**:

$$\text{minimize} \quad {\|\|Ax - b\|\|}^2$$

where $\|\| \cdot \|\|$ denotes the Euclidean (L2) norm. This is the **least squares problem**, where we want to find $x$ that minimizes the sum of the squared differences between the predicted values $Ax$ and the observed values $b$.

### Solving the Least Squares Problem with QR Factorization

The **QR factorization** of the matrix $A$ can be used to solve the least squares problem efficiently. If we perform the QR decomposition on $A$, we obtain:

$$A = QR$$

where:
- $Q$ is an $m \times m$ orthogonal matrix, whose columns are orthonormal vectors.
- $R$ is an $m \times n$ upper triangular matrix, where the first $n$ rows form an $n \times n$ upper triangular matrix and the remaining rows are zero.

### Steps to Solve the Least Squares Problem

To solve the least squares problem using QR factorization, follow these steps:

1. Compute the QR Decomposition of $A$.
2. Set up the Normal Equations:
	- Using the fact that $A = QR$, substitute this into the least squares objective function:
   $${\|\|Ax - b\|\|}^2 = {\|\|QRx - b\|\|}^2$$
   - Since $Q$ is an orthogonal matrix, $Q^T Q = I$, so this simplifies to: 
   $${\|\|QRx - b\|\|}^2 = {\|\|Rx - Q^T b\|\|}^2$$

3. Solve the Triangular System:
   - The equation ${\|\|Rx - Q^T b\|\|}^2$ is now a system of equations with $R$ being upper triangular. To find $x$, we solve the triangular system:
   $$Rx = Q^T b$$
   - Since $R$ is upper triangular, this system can be solved efficiently using **back substitution**.
  
### Example

Suppose we have the overdetermined system:

$$A = \begin{bmatrix} 1 \& -1 \& 4 \\\ 1 \& 4 \& -2 \\\ 1 \& 4 \& 2 \\\ 1 \& -1 \& 0 \end{bmatrix}, \quad b = \begin{bmatrix} 2 \\\ -3 \\\ 5 \\\ 1 \end{bmatrix}$$

1. **QR Decomposition**:

$$A = QR = \frac{1}{2}\begin{bmatrix}1 \& -1 \& 1 \\\ 1 \& 1 \& -1 \\\ 1 \& 1 \& 1 \\\ 1 \& -1 \& -1\end{bmatrix}\begin{bmatrix}2 \& 3 \& 2 \\\ 0 \& 5 \& -2 \\\ 0 \& 0 \& 4\end{bmatrix}$$

3. **Solve the Least Squares Problem**:

   - Once we have $Q$ and $R$, solve the system $Rx = Q^T b$ using back substitution.

$$\begin{bmatrix}2 \& 3 \& 2 \\\ 0 \& 5 \& -2 \\\ 0 \& 0 \& 4\end{bmatrix}\begin{bmatrix}x_1 \\\ x_2 \\\ x_3\end{bmatrix} = \frac{1}{2}\begin{bmatrix}1 \& 1 \& 1 \& 1 \\\ -1 \& 1 \& 1 \& -1 \\\ 1 \& -1 \& 1 \& -1\end{bmatrix}\begin{bmatrix} 2 \\\ -3 \\\ 5 \\\ 1 \end{bmatrix} = \begin{bmatrix} 2.5 \\\ -0.5 \\\ 4.5 \end{bmatrix}$$

$$\begin{cases} x_1 = -0.4 \\\ x_2 = 0.35 \\\ x_3 = 1.125\end{cases}$$
