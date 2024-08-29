# conjugate_gradient


The Conjugate Gradient method is an iterative algorithm used for solving systems of linear equations of the form:
A x = b
where:
A is a symmetric positive-definite matrix.
x is the vector of unknowns.
b is the right-hand side vector.

Goal: The goal is to find the vector x that minimizes the quadratic form:
f(x) = (1/2) x^T A x - b^T x

Properties:
The Conjugate Gradient method is particularly effective for large, sparse systems.
It leverages the properties of the matrix A to minimize the error efficiently.
The method converges in at most n iterations, where n is the size of the matrix A.


Choose an initial guess x_0 (often x_0 = 0).

Compute the initial residual:
r_0 = b - A x_0

Set the initial search direction:
p_0 = r_0

Iteration:
For k = 0, 1, 2, ... until convergence:

Compute A p_k:
A p_k = A p_k

Calculate the step size alpha_k:
alpha_k = (r_k^T r_k) / (p_k^T A p_k)

Update the solution:
x_{k+1} = x_k + alpha_k p_k

Update the residual:
r_{k+1} = r_k - alpha_k A p_k
Check for convergence. If ||r_{k+1}|| < tolerance, stop.

Calculate the new search direction:
beta_k = (r_{k+1}^T r_{k+1}) / (r_k^T r_k)
p_{k+1} = r_{k+1} + beta_k p_k

Convergence:
The algorithm converges when the residual r_k is sufficiently small, indicating that A x_k is close to b.

Time Complexity:
The time complexity of the Conjugate Gradient method is O(n^2) for each iteration, where n is the number of variables. The total number of iterations required for convergence depends on the condition number of the matrix A.


The Conjugate Gradient method is suitable for large-scale problems where direct methods (like Gaussian elimination) are impractical.
It is particularly useful in numerical simulations and optimization problems, especially in finite element methods.
