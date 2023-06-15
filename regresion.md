# lin_mod_R_julian_c02

# Estimation

## 2.1 Linear Model

Suppose we want to model the response Y in terms of three predictors, $X_1, X_2$ and $X_3$. One
very general form for the model would be:

$$
Y= f(X_1, X_2, X_3) + \varepsilon
$$

where f is some unknown function and " is the error in this representation. " is additive in
this instance, but could enter in some more general form. Still, if we assume that f is a
smooth, continuous function, that still leaves a very wide range of possibilities. Even with
just three predictors, we typically will not have enough data to try to estimate f directly.

So we usually have to assume that it has some more restricted form, perhaps linear as in:

$$
Y= \beta_0 + \beta_1 X_1 + \beta_2 X_2+ \beta_3 X_3 + \varepsilon
$$


where $\beta_i$, i=0, 1, 2, 3 are unknown parameters. $\beta_0$ is called the intercept term. Thus the
problem is reduced to the estimation of four parameters rather than the infinite
dimensional f. In a linear model the parameters enter linearly—the predictors themselves
do not have to be linear. For example:

$$
Y= \beta_0 + \beta_1 X_1 + \beta_2 \log X_2+ \beta_3 X_1 X_2 + \varepsilon
$$

is a linear model, but:

$$
Y= \beta_0 + \beta_1 X_1^{\beta_2} + \varepsilon
$$

is not. Some relationships can be transformed to linearity—for example, $y = \beta_0 x_1^{\beta}\varepsilon$
can
be linearized by taking logs. Linear models seem rather restrictive, but because the
predictors can be transformed and combined in any way, they are actually very flexible.
The term linear is often used in everyday speech as almost a synonym for simplicity. This
gives the casual observer the impression that linear models can only handle small simple
datasets. This is far from the truth—linear models can easily be expanded and modified
to handle complex datasets. Linear is also used to refer to straight lines, but linear models
can be curved. Truly nonlinear models are rarely absolutely necessary and most often
arise from a theory about the relationships between the variables, rather than an empirical
investigation.


## 2.2 Matrix Representation

If we have a response Y and three predictors, $X_1, X_2$ and $X_3$, the data might be presented
Downloaded by [University of Toronto] at 16:20 23 May 2014
in tabular form like this:

\begin{matrix}
y_1 & x_{11}  & x_{12}  & x_{13}  \\ 
y_2 & x_{21}  & x_{22}  & x_{23}  \\
... & ...  & ...  & ...  \\ 
y_n & x_{n1}  & x_{n2}  & x_{n3}   
\end{matrix}

where n is the number of observations, or cases, in the dataset.

Given the actual data values, we may write the model as:

$$
y_i= \beta_0 + \beta_1x_{1i}+\beta_2x_{2i}+ \beta_3x_{3i}+\varepsilon_i i=1,…, n
$$

but the use of subscripts becomes inconvenient and conceptually obscure. We will find it
simpler both notationally and theoretically to use a matrix/vector representation. The
regression equation is written as:

$$
y=X\beta + \varepsilon
$$

where $y=(y_1,…, y_n)^T$, $\varepsilon =(\varepsilon_1, ..., \varepsilon_n)^T$, $\beta=(\beta_0,…,\beta_3)^T$ and:

$$
X = \begin{pmatrix}
1 & x_{11} & x_{12} & x_{13} \\ 
1 & x_{21} & x_{22} & x_{23} \\ 
... & ... & ... & ... \\ 
1 & x_{n1} & x_{n2} & x_{n3} \\ 
\end{pmatrix}
$$

The column of ones incorporates the intercept term. One simple example is the null
model where there is no predictor and just a mean $y= \mu + \varepsilon$:

$$
\begin{pmatrix}
y_1  \\ 
...  \\ 
y_n  
\end{pmatrix} = \begin{pmatrix}
1  \\ 
...  \\ 
1  
\end{pmatrix} \mu + \begin{pmatrix}
\varepsilon_1  \\ 
...  \\ 
\varepsilon_n  
\end{pmatrix}
$$


We can assume that E"=0 since if this were not so, we could simply absorb the nonzero
expectation for the error into the mean ! to get a zero expectation.

## 2.3 Estimating $\beta$

The regression model, $y= X \beta + \varepsilon$, partitions the response into a systematic component $X\beta$
and a random component $\varepsilon$ We would like to choose $\beta$ so that the systematic part explains as much of the response as possible. Geometrically speaking, the response lies in an n-dimensional space, that is, $y \in R^n$
while $\beta \in R^p$
where p is the number of parameters.
If we include the intercept then p is the number of predictors plus one. We will use this
definition of p from now on. It is easy to get confused as to whether p is the number of
predictors or parameters, as different authors use different conventions, so be careful.

The problem is to find $\beta$ so that $X\beta$ is as close to Y as possible. The best choice, the
estimate $\hat{\beta}$, is apparent in the geometrical representation seen in Figure 2.1.

$\hat{\beta}$ is, in this sense, the best estimate of ! within the model space. The response predicted
by the model is $\hat{y} = X \hat{\beta}$
or Hy where H is an orthogonal projection matrix. The difference

between the actual response and the predicted response is denoted by and is called the
residuals.

The conceptual purpose of the model is to represent, as accurately as possible,
something complex, y, which is n-dimensional, in terms of something much simpler, the
model, which is p-dimensional. Thus if our model is successful, the structure in the data
should be captured in those p dimensions, leaving just random variation in the residuals
which lie in an (n#p)-dimensional space. We have:


Data=Systematic Structure+Random Variation
n dimensions=p dimensions+(n#p)dimensions

## 2.4 Least Squares Estimation

The estimation of $\beta$ can also be considered from a nongeometrical point of view. We
might define the best estimate of $\beta$ as the one which minimizes the sum of the squared
errors. The least squares estimate of $\beta$, called $\hat{\beta}$ minimizes:


$$
\sum \varepsilon_i^2 = \varepsilon^T \varepsilon = (y - X \beta)^T (y - X\beta) 
$$

Differentiating with respect to ! and setting to zero, we find that $\hat{\beta}$
satisfies:

$$
X^TX\hat{\beta} = X^T y
$$

These are called the normal equations. We can derive the same result using the
geometrical approach. Now provided $X^TX$ is invertible:

$$
\hat{\beta} = (X^TX)^{-1}X^Ty \\
\hat{\beta} = (X^TX)^{-1}X^Ty \\

$$






