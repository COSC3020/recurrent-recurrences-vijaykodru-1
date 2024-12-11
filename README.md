# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

Let's consider the equation  $T(n) = T\left(\frac{n}{13}\right) + 5$

lets substitute n = n/13

we get $T(n/13) = T(n/13^2) + 5$

as we keep doing this we get the generalized form as below:

$T(n) = T(n/13^i) + 5i$

recursion stops when $n/13^i = 1$ from this we get $i = log_(13)(n)$ and we know that $13^(log_13(n)) = n$

substitute: = $T(n/13^(log_13(n))) + 5(log_13(n))$
            = $T(1) + 5(log_13(n))$

Therefore the Big Theta complexity is $\Theta(logn)$

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

if we do the same thing as we did for the first one we can get the generalized form as:

$T(n) = 13^iT(n/13^i) + 5\sum_(i = 0)(n - 1) 13^i$

recursion stops when $n/13^i = 1$ from this we get $i = log_(13)(n)$ and we know that $13^(log_13(n)) = n$

$T(n) = n + 5\left(\frac{13^{i} - 1}{13 - 1}\right)$

$T(n) = n + 5\left(\frac{n - 1}{12}\right)$

Therefore the Big Theta complexity is $\Theta(n)$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$


if we do the same thing as we did for the first two problems we get the Big Theta complexity is $\Theta(nlogn)$


Reference:

The last two problems are verified by hand on a paper. 

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice
