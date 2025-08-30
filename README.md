# PA 2 – NumPy Python
## Overview  
This assignment explores the basics of **NumPy** on array manipulation in Python. The program features random array generation, normalization, reshaping, logical indexing, and saving data into `.npy` files.  

## Directory
### Normalization Problem: 
- https://github.com/emmanuelgabriellimeng-hash/PROGRAMMING-ASSIGNMENT-2/blob/main/README.md#normalization-problem-1
### Divisible by 3 Problem:  
- https://github.com/emmanuelgabriellimeng-hash/PROGRAMMING-ASSIGNMENT-2/blob/main/README.md#divisible-by-3-problem-1
### Program Link:
- https://github.com/emmanuelgabriellimeng-hash/PROGRAMMING-ASSIGNMENT-2/blob/main/LIM_2ECEB_Experiment_2.ipynb
---

## Normalization Problem  

**Description:**  
Normalize a random 5×5 ndarray using the formula:  

$$ Z = \frac{X - \bar{X}}{\sigma} $$

where:
- $X$ = data  
- $\bar{X}$ = mean of $X$  
- $\sigma$ = standard deviation of $X$

Save the normalized ndarray as `X_normalized.npy`.  

---  
**Explanation**  

1. Import NumPy library.  
```python
import numpy as np
```  

2. Create a randomized 5×5 ndarray using `np.random.rand()`.  
```python
X = np.random.rand(5, 5)  
```  

3. Apply normalization formula whilst using `X.mean()` and `X.std()` to for the mean and standard deviation respectively.  
```python
X_normalized = (X - X.mean()) / X.std()
```  

4. Save the normalized ndarray to a `.npy` file.  
```python
np.save("X_normalized.npy", X_normalized)
```  

5. Print the Original ndarray, mean, standard deviation, and the normalized ndarray.  
```python
print("Original ndarray:\n", X)                      
print("\nMean:", X.mean(), "\tStd Dev:", X.std())
print("\nNormalized ndarray:\n", X_normalized)
```  

---  
**Example Output:**  
```
Original ndarray:
 [[0.11698285 0.02983347 0.12815127 0.94548841 0.58362847]
 [0.50460234 0.27923148 0.14918422 0.51413625 0.24169649]
 [0.66408114 0.22191292 0.41527691 0.07167181 0.87905917]
 [0.68387476 0.92544118 0.23568685 0.88793083 0.08205872]
 [0.08959668 0.88338079 0.14242905 0.29447202 0.69561394]]

Mean: 0.42661688046667434   Std Dev: 0.30905047863199286

Normalized ndarray:
 [[-1.00188822 -1.28387897 -0.96575035  1.67892161  0.50804512]
 [ 0.25233892 -0.47689752 -0.89769367  0.28318794 -0.59835013]
 [ 0.76836722 -0.66236416 -0.03669294 -1.14850193  1.46397539]
 [ 0.83241378  1.61405443 -0.61779561  1.49268157 -1.11489283]
 [-1.09050211  1.47795892 -0.9195515  -0.42758343  0.87039846]]
```  

---

## Divisible by 3 Problem  

**Description:**  
Create a 10×10 ndarray of the squares of the first 100 positive integers. From this ndarray, extract all elements divisible by 3, then save them into a file named `div_by_3.npy`.  

---  
**Explanation**  

1. Import NumPy library.  
```python
import numpy as np
```  

2. Generate an array of squares of 100 positive integers and reshape into a 10×10 ndarray.  
```python
A = (np.arange(1, 101) ** 2).reshape(10, 10)
```  

3. Use boolean indexing (`A % 3 == 0`) to filter numbers divisible by 3.  
```python
div_by_3 = A[A % 3 == 0]
```  

4. Save the filtered array to a `.npy` file.  
```python
np.save("div_by_3.npy", div_by_3)
```  

5. Print the 10×10 ndarray and the extracted numbers.  
```python
print("Squared Values of 1-100:\n", A)
print("\nElements divisible by 3:\n", div_by_3)
```  

---  
**Example Output:**  
```
Squared Values of 1-100:
 [[    1     4     9    16    25    36    49    64    81   100]
 [  121   144   169   196   225   256   289   324   361   400]
 [  441   484   529   576   625   676   729   784   841   900]
 [  961  1024  1089  1156  1225  1296  1369  1444  1521  1600]
 [ 1681  1764  1849  1936  2025  2116  2209  2304  2401  2500]
 [ 2601  2704  2809  2916  3025  3136  3249  3364  3481  3600]
 [ 3721  3844  3969  4096  4225  4356  4489  4624  4761  4900]
 [ 5041  5184  5329  5476  5625  5776  5929  6084  6241  6400]
 [ 6561  6724  6889  7056  7225  7396  7569  7744  7921  8100]
 [ 8281  8464  8649  8836  9025  9216  9409  9604  9801 10000]]

ELements divisble by 3:
 [   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]
```  

---
