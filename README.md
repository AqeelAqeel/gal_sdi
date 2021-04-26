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

* CDF = lower_SUM_upper p(X = n)

#### Expected value

* Discrete
    * E(X) = SUM_i (x_i * p(x_i))
* Continuous
    * E(X) = -inf_INT_inf (x * f(x))dx

#### Covariance

* Estimates amount and direction Y moves as X changes
* COV(X, Y) = 1/n * i=1_SUM_n (x_i - xBar)(y_i - yBar)

#### Variance

* VAR(X) = COV(X, X) = 1/n * i=1_SUM_n (x_i - xBar) ** 2

#### Correlation coefficient

* corr(X, Y) = [i=1_SUM_n (x_i - xBar)(y_i - yBar)] / SQRT[(i=1_SUM_n (x_i - xBar) ** 2) * (i=1_SUM_n (y_i - yBar) ** 2)

#### Distributions

![Normal](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/c548abe948b204550481654e32b9d4d4.png)

![Empirical Rule](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/7e9688d48ba2b2e304969d13d8e4343d.png)

![Geometric](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/365d2527ed510a5c5bf3d220887aef13.png)

![Power Law](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/b2e012bf689efa1483f296698db3c0f0.png)

![Population and Sampling Distribution](https://s3.us-west-2.amazonaws.com/forge-production.galvanize.com/content/3cd2651378842a8f25f7f70b26ab65a0.png)

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
