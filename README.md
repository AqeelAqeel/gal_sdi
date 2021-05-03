<meta http-equiv="content-type" content="text/html;charset=utf-8" />
<span style="font-family: Menlo;">

# Master Notes

Last Update: 24 Apr 2021

---

## CLI

#### Basic Commands

* make directory: `mkdir [folder name]`
* create file: `touch [file name]`
* move or rename: `mv [old] [new]`
* copy: `cp [old] [new]`
* recursive copy: `cp -r [old] [new]`
* remove: `rm [file name]`
* recursive remove: `rm -r [file name]`
* clear terminal: `cmd + k`

---

## Git & Github

* [git cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf)

#### Basic Commands

* initize repo: `git init`
* clone repo: `git clone [url]`
* add to stage: `git add [filename]`
* commit: `git commit -m "[message]"`
* push: `git push`
* pull: `git pull`
* see all branches: `git branch -a`
* create branch: `git branch [new branch name]`
* switch branches: `git checkout [branch name]`
* create and switch brnaches: `git checkout -b [new branch name]`

#### Advanced Commands

* create a new repository on the command line

```unix
echo "# gal_sdi" >> README.md
git init
git add .
git commit -m "init commit"
git branch -M main
git remote add origin https://github.com/josiah-d/gal_sdi.git
git push -u origin main
```

* push an existing repository from the command line

```unix
git remote add origin https://github.com/josiah-d/gal_sdi.git
git branch -M main
git push -u origin main
```

---

## Maths

### Stats

#### Permutations

* nPk = n! / (n - k)!

#### Combinations

* nCk = n! / ((n - k)!  * k!)

* Complex version
    * (KCk * (N - K)C(n - k)) / NCn
    * Where:
        * K is `number of successes available`
        * k is `number of successes needed`
        * N is `members available`
        * n is `mebers chosen`

#### Conditional probability

* P(A | B) = P(AB) / P(B)

#### Bayes' Theorum

* P(A | B) = (P(B | A) * P(A)) / P(B)

#### Cumulative distribution function

* [CDF resources](https://learn-2.galvanize.com/cohorts/868/blocks/248/content_files/07_Continuous_Prob_Dists/00_unit_overview.md)
* CDF = &Sigma;<sub>lower</sub><sup>upper</sup> p(X = n)
* Normal distribution Z-test: `norm.cdf(1.5, loc=1.25, scale=.46)`

#### Expected value

* Discrete
    * E(X) = &Sigma;<sub>i</sub> (x<sub>i</sub> * p(x<sub>i</sub>))
* Continuous
    * E(X) = &int;<sub>-inf</sub><sup>inf</sup> (x * f(x))dx

#### Mean

* &mu; = n * p

#### Covariance

* Estimates amount and direction Y moves as X changes
* COV(X, Y) = 1/n * &Sigma;<sub>i=1</sub><sup>n</sup> (x<sub>i</sub> - xBar)(y<sub>i</sub> - yBar)

#### Variance

* VAR(X) = COV(X, X) = 1/n * &Sigma;<sub>i=1</sub><sup>n</sup> (x<sub>i</sub> - xBar) ** 2

```python
n = total
p = mean / total
print((n*p) * (1-p))
```

* VAR = n * p * (1 - p)

#### Correlation coefficient

* corr(X, Y) = [&Sigma;<sub>i=1</sub><sup>n</sup> (x<sub>i</sub> - xBar)(y<sub>i</sub> - yBar)] / SQRT[(&Sigma;<sub>i=1</sub><sup>n</sup> (x<sub>i</sub> - xBar) ** 2) * (&Sigma;<sub>i=1</sub><sup>n</sup> (y<sub>i</sub> - yBar) ** 2)

#### Distributions

* Quick sheet sheet on choosing distributions:
    * Q: what's the probability of flipping 10 heads in 25 coin flips?
        * A: binomial
    * Q: what's the probability that the first heads will be on the third flip?
        * A: geometric
    * Q: what's the probability of flipping 20 heads over the course of 13 minutes if on average, you flip 10 heads per minute?
        * A: poisson
    * Q: what's the probability you wait more than a minute before flipping a heads, given that you flip an average of 10 heads per minute?
        * A: exponential

![Normal](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/c548abe948b204550481654e32b9d4d4.png)

![Empirical Rule](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/7e9688d48ba2b2e304969d13d8e4343d.png)

![Geometric](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/365d2527ed510a5c5bf3d220887aef13.png)

![Power Law](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/b2e012bf689efa1483f296698db3c0f0.png)

![Population and Sampling Distribution](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/3cd2651378842a8f25f7f70b26ab65a0.png)

#### Central limit theorem (CLT)

* &mu;_Xbar = &mu;
* &sigma;_Xbar = &sigma; / sqrt(n)

#### Hypothesis testing

* &mu; == `True` population mean 
* &mu;<sub>0</sub> == `hypothesized` population mean 

* Null hypothesis (H<sub>0</sub>)
    * the initial claim, assumption, presumption, or assertion being made
    * H<sub>0</sub> : &mu; == &mu;<sub>0</sub>
* Alternative hypothesis (H<sub>A</sub>)
    * An alternative that can be accepted if there is statistically significant evidence found to refute the null hypothesis
    * Upper tailed
        * H<sub>A</sub> : &mu; > &mu;<sub>0</sub>
    * Lower tailed
        * H<sub>A</sub> : &mu; < &mu;<sub>0</sub>
    * Two tailed
        * H<sub>A</sub> : &mu; != &mu;<sub>0</sub>
    * Errors
        * Type I
            * Reject H<sub>0</sub> when it is `True`
        * Type II
            * Accept H<sub>0</sub> when it is `False`
* t-statistic
    * t = (xBar - &mu;<sub>0</sub>) / (s / sqrt(n)) * t(n - 1)

#### Confidence intervals

* Used when there are no preconceived notions and desire to use sampling to learn about the population
![95% CI](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/21125c3404bf0e14de6dcc164f71e5b1.png)

### Linear algebra

#### Matrix multiplication

* (AB)<sub>ij</sub> = &Sigma;<sub>k=1</sub><sup>m</sup> a<sub>ik</sub> * b<sub>kj</sub>
* Dot product: A.dot(b) = A * B<sup>T</sup>

#### Identity matrix (I<sub>m</sub>)

* They are square, same number of rows and columns
* They are diagonal, only non-zero entries have the same row and column index
* All non-zero entries are 1

![Identity Matrix](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse1.mm.bing.net%2Fth%3Fid%3DOIP.kVdcPRjTiGUVjok2dRNhKAHaBx%26pid%3DApi&f=1)

#### Matrix rank & independence

* Linear dependence
    * Column can be constructed from other columns' data
* Linear independence
    * Unique data that cannot be constructed from other rows
* Rank
    * Number of linear independent columns (or rows) in a matrix

#### Invertible matrix

* `np.linalg.inv(MATRIX)`
* AA<sup>-1</sup> = A<sup>-1</sup>A = I
* It must be square, i.e. of size `n X n`
* It must be full-rank, i.e. the number of linearly independent rows/columns is equal to `n`
* Square matrices that stretch and/or rotate vectors without any collapsing of dimensions are invertible

#### Matrix rotation

R = [[cos(&theta;), -sin(&theta;)], [sin(&theta;), cos(&theta;)]]

* Testing

R * [[1], [0]] = [[cos(&theta;)], [sin(&theta;)]]

**Radians**: &theta; = arcos(x) = arcsin(y) = arctan(y/x)
**Degrees**: [&theta; = arcos(x) = arcsin(y) = arctan(y/x)] * (180/&pi;)

![Unit Circle](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fwww.shelovesmath.com%2Fwp-content%2Fuploads%2F2012%2F11%2FUnit-Circle.png&f=1&nofb=1)

#### Systems of equations with linear algebra

Ax<sup>&rarr;</sup> = b<sup>&rarr;</sup>
A<sup>-1</sup>Ax<sup>&rarr;</sup> = A<sup>-1</sup>b<sup>&rarr;</sup>
Ix<sup>&rarr;</sup> = x<sup>&rarr;</sup> = A<sup>-1</sup>b<sup>&rarr;</sup>

* Where
    * A is a matrix of coeff
    * x<sup>&rarr;</sup> is an unknown vector
    * b<sup>&rarr;</sup> is there product
    * A<sup>-1</sup> is an inverse matrix
    * I is an identity matrix

* Sample code

```python
A = np.array(matrix)
b = np.array(vector)
A_1 = np.linalg.inv(A)
I = A @ np.linalg.inv(A)
x = A_1.dot(b)

print(x)
```

#### Vector similiarity

* Euclidean distance
    * Distance between p<sup>&rarr;</sup> and q<sup>&rarr;</sup>
    * Displays relative magnitudes

d(p<sup>&rarr;</sup>,q<sup>&rarr;</sup>) = sqrt((q<sub>1</sub>-p<sub>1</sub>)<sup>2</sup>+(q<sub>2</sub>-p<sub>2</sub>)<sup>2</sup>+...+(q<sub>n</sub>-p<sub>n</sub>)<sup>2</sup>) = sqrt((q<sup>&rarr;</sup>-p<sup>&rarr;</sup>)<sup>2</sup>)

`euc_dist = dot(a,b) / (norm(a) * norm(b))`

```python
import pandas as pd
import numpy as np

# Don't alter the code below
np.random.seed(1)
vec1 = pd.Series(np.random.randint(0, 10, 35))
vec2 = pd.Series(np.random.randint(10, 20, 35))

# Your code below
euc_dist = sum((vec1 - vec2)**2)**.5
```

* L2- Norm

||p<sup>&rarr;</sup>|| = sqrt(p<sub>1</sub><sup>2</sup>+p<sub>2</sub><sup>2</sup>+...+p<sub>n</sub><sup>2</sup>) = sqrt(p<sup>&rarr;</sup><sup>2</sup>)

* Normalize a data set

```python
from sklearn.datasets import load_iris
import numpy as np

iris_data = load_iris()['data']

min_ = iris_data.min(axis=0)
ptp = iris_data.ptp(axis=0)

iris_data_normalized = np.round((iris_data - min_) / ptp , 2)
```

* Cosine similarity
    * Displays direction

p<sup>&rarr;</sup>*q<sup>&rarr;</sup> = ||p<sup>&rarr;</sup>|| * ||q<sup>&rarr;</sup>|| * cos&Theta;

* Where &Theta; is the angle between the vectors
* 1 = aligned, -1 = opposite, 0 = orthogonal

sim(p<sup>&rarr;</sup>,q<sup>&rarr;</sup>) = cos&Theta; = p<sup>&rarr;</sup> * q<sup>&rarr;</sup> / ||p<sup>&rarr;</sup>|| * ||q<sup>&rarr;</sup>||

##### Eigenvectors and Eigenvalues

* Eigenvectors must be square matrices and satisfy:

Av<sup>&rarr;</sup> = &lambda;v<sup>&rarr;</sup>

* Where &lambda; is a scalar, e.g. the eigenvalue

### Differntial calculus

#### Limits

lim<sub>x&rarr;a</sub> f(x) = L

![Limit](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/7f7dedfbccb1f194dfc0b1d484244008.png)

#### Derivatives

(f(x+h) - f(x)) / h = &Delta;f / &Delta;x

f'(x) = lim<sub>h&rarr;0</sub> (f(x+h) - f(x)) / h = lim<sub>&Delta;x&rarr;0</sub> &Delta;f / &Delta;x = d/dx f(x)

![Derivative](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/25aa43c1b0c93527738ab55c6ac65c6d.png)

#### Power rule

d/dx x<sup>n</sup> = nx<sup>n-1</sup>

#### Chain rule

f(x) = h(x) * g(x) = h(g(x))

f'(x) = h'(g(x)) * g'(x)

**or**

du/dx = (du/dv) * (dv/dx)

### Integral calculus

#### Antiderivative

F(x) = &int;f(x) dx

#### Power rule

&int;x<sup>n</sup> dx = x<sup>n+1</sup> / (n+1) + C

#### Indefinite integrals by substitution

f(g(x)) = &int;f'(g(x))g'(x) dx

#### Reimann summation

area = &Sigma;<sub>i=0</sub><sup>n-1</sup> f(x<sub>i</sub>)&Delta;x

* Sample code

```python
import numpy as np


# Define the function you're integrating
def f(x):
    return np.sqrt(x**3) / (x ** 3 + 6)


# Define an integration function
def riemann_sum(f, a, b, n):
    """Approximate the area under the curve 'f' from 'a' to 'b' via
    a Riemann summation of 'n' rectangles using the midpoint rule.

    Parameters
    ----------
        f : function
            The function over which to integrate
        a : float
            The lower bound of the integral
        b : float
            The upper bound of the integral
        n : int
            The number of rectangles to use

    Returns
    -------
        float
            An approximation of the definite integral
            of 'f' over the interval ['a', 'b'].
    """
    # The width of the rectangles, delta x
    dx = (b - a) / n

    # A length-n vector of x-values starting at a + dx/2 and ending at b - dx/2
    xi = np.linspace(a + 0.5*dx, b - 0.5*dx, n)

    # A length-n vector of just dx ([dx, dx, ...])
    dx_vec = np.array([dx]*n)

    # Evaluate f(x) for all xi values
    fxi = f(xi)

    # Return the dot product of f(xi) the vector of [dx, dx, ...]
    # This is just a quick and easy way to take the sum of the
    # products f(x_i)*dx
    return np.dot(fxi, dx_vec)


# Call riemann_sum() with the correct arguments
approx_area = riemann_sum(f, 0, 10, 100)
print(approx_area)
```

* Limit

dx = &Delta;x&rarr;0 = lim<sub>n&rarr;&infin; (b-a) / n

* Probability density function

f(x) = (2 * &pi;)<sup>-1/2</sup> * e <sup>(-1/2) * x<sup>2</sup></sup>

* y-axis symmetry

&int;<sub>-a</sub><sup>a</sup> f(x) dx = 2 &int;<sub>0</sub><sup>a</sup> f(x) dx

* Monte Carlo integrator

```python
import numpy as np


# Define the standard normal distribution pdf function
def std_nrm_pdf(x):
    return np.exp(-x**2 / 2) / (np.sqrt(2 * np.pi))


# Define the Monte Carlo integrator for an even function
def monte_carlo(f: callable, x_bound: float, y_bound: float, n: int) -> float:
    """A basic Monte Carlo integrator.

    Note: this integrator assumes that f is an even function,
    that the bounds of integration are -x_bound to x_bound,
    and that f(x) >= 0 for all x between 0 and x_bound.

    Parameters
    ----------
    f : callable
        The function object whose definite integral MC approximates.
    x_bound : float
        The horizontal bound of the integrating domain.
    y_bound : float
        The vertical bound of the integrating domain.
    n : int
        The number of random points to generate in the domain.

    Returns
    -------
    float
        The approximate area under f between -x_bound and x_bound.
    """
    area_dom = x_bound * y_bound

    # Generate vectors of random x- and y-values, scaled by
    # their respective bounds
    x_vals = x_bound * np.random.rand(n)
    y_vals = y_bound * np.random.rand(n)

    # Use a boolean mask y <= f(x) to get a new vector of only
    # the values where that condition is true
    ratio = len(y_vals[y_vals <= f(x_vals)]) / n

    return 2 * area_dom * ratio



# x_bound is 2 because that's the upper bound of integration
# y_bound is std_nrm_pdf(0) which for the standard normal
# distribution is the max value of std_nrm_pdf.
x_b = 2.0
y_b = std_nrm_pdf(0)


print(monte_carlo(f=std_nrm_pdf, x_bound=x_b, y_bound=y_b, n=10000))
```

* Integral between two points

&int;<sub>a</sub><sup>b</sup> f(x) - g(x) dx

---

## Plotting

* [Pyplot Docs](https://matplotlib.org/stable/tutorials/introductory/pyplot.html)
* Key parts
    * Title
    * Axes
    * Data
    * Legend
    * Annotations
    * Facets

![PyPlot Parts](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/cdbb5b1b140a97b8ea83e687457cab1a.png)

---

## SQL Databases

* Read sql file

`.read filename.sql`

* Table Summary

`PRAGMA table_info(tablename);`

* Between

```sql
SELECT * FROM table_name
WHERE column_name BETWEEN low AND high;
```

* Group By

```sql
SELECT column_name FROM table_name
GROUP BY column_name;
```

* Order By

```sql
SELECT column_name, other_column_name FROM table_name
ORDER BY other_column_name;
```

* Select Distinct
    * Removes **dulicated** query results

```sql
SELECT DISTINCT column_name, other_column_name FROM table_name
ORDER BY other_column_name;
```

* Aggregate functions
    * `COUNT`

    ```sql
    SELECT other_column_name, COUNT(column_name) FROM table_name
    GROUP BY other_column_name;
    ```

    * `SUM`

    ```sql
    SELECT SUM(column_name) FROM table_name
    GROUP BY other_column_name;
    ```

    * `AVERAGE`

    ```sql
    SELECT AVG(column_name), other_column_name FROM table_name
    GROUP BY other_column_name;
    ```

    * `MIN`

    ```sql
    SELECT MIN(column_name), other_column_name FROM table_name
    GROUP BY other_column_name;
    ```

    * `MAX`

    ```sql
    SELECT MAX(column_name), other_column_name FROM table_name
    GROUP BY other_column_name;
    ```

* Join functions
    * `JOIN`
        * Inner Join

    ```sql
    SELECT t1.col1, t1.col2, t2.col1, t2.col2
    FROM table1 as t1
    JOIN table2 as t2
    ON t1.id = t2.col_id;
    ```

    * `LEFT JOIN`

    ```sql
    SELECT t1.col1, t1.col2, t2.col1, t2.col2
    FROM table1 as t1
    LEFT JOIN table2 as t2
    ON t1.id = t2.col_id;
    ```

    * `RIGHT JOIN`

    ```sql
    SELECT t1.col1, t1.col2, t2.col1, t2.col2
    FROM table1 as t1
    RIGHT JOIN table2 as t2
    ON t1.id = t2.col_id;
    ```

    * `FULL OUTER JOIN`

    ```sql
    SELECT t1.col1, t1.col2, t2.col1, t2.col2
    FROM table1 as t1
    FULL OUTER JOIN table2 as t2
    ON t1.id = t2.col_id;
    ```

    * **Multiple Joins**

    ```sql
    SELECT t1.col1, t1.col2, t2.col1, t2.col2, t3.col1, t3.col2
    FROM table1 as t1
    JOIN table2 as t2
    ON t1.id = t2.col_id
    JOIN table3 as t3
    ON t2.col2_id = t2.id
    ```

* Pick MAX count of GROUP BY table

    ```sql
    /*
    COUNT is given a variable name to allow it to be called later.
    */
    SELECT group_column, COUNT(*) as cnt
    FROM table
    GROUP BY group_column
    ORDER BY cnt DESC
    LIMIT 1;
    ```

---

## Numpy

* Remove rows w/ np.nan

```python
# Imports
from sklearn.datasets import load_diabetes
from random import choice
from random import seed
import numpy as np

# Do not change the code below
seed(1)
diabetes = load_diabetes()['data']
x_miss_idx = [choice(range(diabetes.shape[0])) for _ in range(10)]
y_miss_idx = [choice(range(diabetes.shape[1])) for _ in range(10)]

for x, y in zip(x_miss_idx, y_miss_idx):
    diabetes[x,y] = np.nan

# Your code below, the data is in the variable 'diabetes'
mask = np.any(np.isnan(diabetes) | np.equal(diabetes, 0), axis=1)
dbts_rmv_nan = diabetes[~mask]
```

---

## Vernacular

### Inputs

* Explanatory Variable
* Independent Variable
* Controlled Variable
* Manipulated Variable
* Exposure Variable
* Predicated Variable
* Treatment Variable
* Input Variable
* Regressor (common in Statistics)
* Predictor (common in Data Science)
* Covariate
* Exogenous (from econometrics)

### Output

* Response Variable
* Dependent Variable
* Regressand (common in Statistics)
* Criterion
* Predicted Variable
* Measured Variable
* Explained Variable
* Experimental Variable
* Responding Variable
* Outcome Variable
* Output Variable
* Target (very common in Data Science)
* Label (very common in Data Science)

---

## Python

#### Type hint

```python
def factorial(n: int) -> int:
    prod = 1
    for num in range(1, n + 1):
        prod *= num
    return prod

>>> help(factorial)
Help on function factorial in module __main__:

factorial(n: int) -> int
```

</span>
