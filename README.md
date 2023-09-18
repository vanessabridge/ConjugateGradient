# ConjugateGradient

The following is an implementation of a conjugate gradient method 
that uses Moreau Yosida Regularization to solve non-convex non smooth problems. That means that the functions '''f(x)''' defining these problems are not differentiable and standard approaches such as Steepest Descent or Conjugate Gradient would not be applicable. There are a number of defined problems that can be used to test the algorithms that solve non differentiable functions. 
A set of selected tests are used for this repo and can be found in the notebook.
Ex:
```
def mxhlib(x_0):
  a = len(x_0+1)
  sum_i = np.zeros(a)
  for i in range(1,a):
    sum_j = 0
    for j in range(1,50):
      sum_j = sum_j+ x_0[i]/(j+i-1)
    sum_i[i]=sum_j
  return max(sum_i)
```



## Results

An implementation of the memory algorithm is compared to other optimization solvers is presented in the table below: Simplex method and other Gradient Descent Algorithms

| P  |  n | Memory Algorithm |  CG Method  | Simplex Method | Expected Value |
| -- | -- | ---------------- | ----------- | -------------- | -------------- |
|1   | 20 |   100/28.4272    | 100/114.6783| 100/307.8883   |        0       |
|1   | 20 |   200/28.3831    | 200/112.8467| 200/256.1166   |        0       |
|3   | 20 |    20/-1.4142    |  20/0.8237  |   20/-1.3941   |     -1.4142    |
|3   | 20 |    40/-1.4142    |  40/0.8237  |   40/-1.4138   |     -1.4142    |
|6   | 20 |    20/-1.0000    |  20/-8.3245 |   20/-1.4000   |        -1      |
|6   | 20 |    40/-1.0000    | 40/-12.48845|   40/-0.9999   |        -1      |


