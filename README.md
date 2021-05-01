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

#### Table Summary

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
</span>