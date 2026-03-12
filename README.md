# Polynomial Function Approximation via Taylor Series

## Project Overview

The goal of this project is to demonstrate **Taylor's Theorem** by implementing an approximation engine, which proves that complex, non-polynomial functions can be expressed as infinite polynomials.

This project uses Calculus to derive the exact polynomial construction of a function based on its behavior at a single point. It visualizes how adding higher-degree terms converges the approximation to the target function.

---

## Theoretical Background

### Taylor's Theorem

Taylor's Theorem states that any function $f(x)$ that is infinitely differentiable at a real number is the sum of its Taylor series. This allows us to convert complex functions into simple sums of powers.

Formally, the Taylor series of a function $f(x)$ that is infinitely differentiable at a point $x_0$ is the power series:

$$
P_N(x) = \sum_{n=0}^{N} \frac{f^{(n)}(x_0)}{n!} (x - x_0)^n
$$

Where:
* $f^{(n)}(x_0)$ is the $n$-th derivative of $f$ evaluated at the center $x_0$.
* $N$ is the degree of the polynomial approximation.

---

### Transcendental Functions as Infinite Polynomials

A core demonstration of this project is showing that transcendental functions, which cannot be calculated using finite algebra, are actually **infinite polynomials**. When we center the approximation at $x_0 = 0$, clear patterns emerge in the coefficients that define the geometry of the functions.

#### 1. The Sine Function
The sine function is an **odd function**, meaning it is symmetric with respect to the origin $(\sin(-x) = -\sin(x))$. Consequently, its polynomial expansion contains only odd powers of $x$. The signs alternate to create the oscillating wave pattern.

**Polynomial Expansion:**

$$
\sin(x) = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \dots
$$

**Infinite Sum Definition:**

$$
\sin(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!} 
$$


#### 2. The Cosine Function
The cosine function is an **even function**, meaning it is symmetric with respect to the y-axis $(\cos(-x) = \cos(x))$. Its expansion contains only even powers of $x$. Like sine, the signs alternate to bound the function between -1 and 1.

**Polynomial Expansion:**

$$
\cos(x) = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \dots
$$

**Infinite Sum Definition:**

$$
\cos(x) = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n}}{(2n)!} 
$$


#### 3. The Exponential Function
The natural exponential function is unique because it is its own derivative. Its expansion contains every integer power of $x$. Since all terms are positive $($for $x>0)$, the function grows without bound rather than oscillating.

**Polynomial Expansion:**

$$
e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} + \dots
$$

**Infinite Sum Definition:**

$$
e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}
$$

---

### Lagrange Error Bound

The approximation is rarely perfect for a finite $N$. The difference between the actual function and the polynomial is the Remainder term $R_N(x)$.

If we approximate $f(x)$ with a degree $N$ polynomial, the error is:

$$
R_N(x) = f(x) - P_N(x) = \frac{f^{(N+1)}(z)}{(N+1)!}(x - x_0)^{N+1}
$$

for some real number $z$ between $x$ and $x_0$. As $N \to \infty$, this error term goes to 0 for convergent functions.

---

## Limitations

| Limitation | Description                                                                                                                                                                                   |
| :--- |:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Radius of Convergence** | Not all series converge everywhere. For example, the series for $\ln(x)$ centered at $x=1$ only converges for $0 < x \le 2$. Outside this range, the approximation explodes towards infinity. |
| **Differentiability** | The function must be $C^\infty$ (smooth). Functions with kinks (like $\vert x\vert$ at 0) or discontinuities cannot be approximated via Taylor Series at those points.                        |
| **Local Accuracy** | Taylor series are local approximations. They are incredibly accurate near $x_0$ but require significantly higher degrees $N$ to maintain accuracy as you move further away from the center.   |

---

## Getting Started

### Prerequisites
* Python 3.8+
* Jupyter Notebook

### Installation

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/mattia-3rne/polynomial-function-approximation-via-taylor-series.git
    ```

2.  **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3.  **Launch Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```

---

## Project Structure

* `main.ipynb`: The main analysis notebook.
* `requirements.txt`: Python package dependencies.
* `README.md`: Project documentation.
