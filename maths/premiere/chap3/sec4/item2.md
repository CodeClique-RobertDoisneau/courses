### ⭐ **EPM342 - Exercice 2 : Suite de Fibonacci**

*Notions : suite recurente d'ordre deux*  

On vas étudier une suite celebre en mathmatiques qui s'apelle la suite de Fibonacci et qui survient dans de nombreux probleme complexe. Elle se definit en langage naturel de cette maniere : mes termes se calcul par la somme de mes deux antecedants. 

Ainsi :

$$ u_{n+2} = u_{n+1} + u_{n}, \hspace{1em}u_{0} = u_{1} = 1 $$


## I/ Exercice

1. Completer le code suivant pour calculer la suite de Fibonacci


```python
def fibo(n): 
    a = 1
    b = 1
    for i in range(...):
        c = ... + ...
        a = b
        b = ...
    return b
```