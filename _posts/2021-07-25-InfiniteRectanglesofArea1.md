---
title: 'A Phenominal Geometrical Limit!'
date: 2021-07-27
permalink: /posts/2021/07/math-blog-1/
tags:
  - Infinite Series
  - Wallis Product
  - Recursive Relations
---

Problem Statement
------
*Begin with a rectangle $R_{1}$ of $Area = 1$ such that both its sides, the horizontal length $L_{1}$ and vertical width $W_{1}$, are equal to 1. Next, Perform the following two steps:*
*<br /><br />1. Add a rectangle of $Area = 1$ adjacent to the right side of R1 such that both rectangles now have a common width.*
*<br />2. Add another rectangle of $Area = 1$ adjacent to the top of both these rectangles such that the length of this rectangle is equal to the sum of the lengths of the bottom rectangles. The outer boundary of these three adjacent rectangles is a new rectangle. Call it $R_{2}$.*
*<br /><br />Repeat these steps infinitely many times. Take the rectangle $R_{n}$ at step $n$, add a rectangle of unit Area to to its right and another rectangle of unit Area to the top of both these rectangles, the outer boundary of these three rectangles will give you $R_{n+1}$, what does the ratio of the Length $L_{n}$ to Width $W_{n}$ of Rectangle $R_{n}$ approach as $n$ grows indefinitely? Or in other words, evaluate the following limit:*  

$$ \lim_{n \to \infty} L_{n}/W_{n} =  ? $$

Solution #1 (Engineer's Way)
------
![figure_1](/files/rectangle_problem.png "Fig. 1")

Observe that at iteration $n+1$, the width of rectangle being added to the right of $R_{n}$ is the same as the width of $R_{n}$ since they are adjacent. Given that the Area of this rectangle being added is $1$, its horizontal length must be the multiplicative reciprocal of its width. From the diagram given above, we can say that:

$$ dL_{n} = \frac{1}{W_{n}} $$

The sum of $L_{n}$ and $dL_{n}$ yield the new length, $L_{n+1}$, for the new Rectangle $R_{n}$. The second rectangle we add at the top must also have an Area of $1$, and since its length is the same as Rectangle $R_{n+1}$, its width $dW_{n}$, by the same argument as $Equation (2)$ will be given as:

$$ dW_{n} = \frac{1}{L_{n+1}} $$

The new Length $L_{n+1}$ and Width $W_{n+1}$ of the Rectangle $R_{n+1}$ are given as following:

$$ L_{n+1} = L_{n} + dL_{n} = L_{n} + \frac{1}{W_{n}} $$

$$ W_{n+1} = W_{n} + dW_{n} = W_{n} + \frac{1}{L_{n+1}} $$

We will simplify the expression for $L_{n+1}$ since $W_{n+1}$ also depends on it. We observe that the product of $W_{n}$ and $L_{n}$ is just the area of the previous rectangle, $R_{n}$, and we express that as $A_{n}$.

$$ L_{n+1} = L_{n} + \frac{1}{W_{n}} = \frac{L_{n}W_{n} + 1}{W_{n}} $$

$$ L_{n+1} = \frac{A_{n} + 1}{W_{n}} $$

Next we try to simplify the $W_{n+1}$ relation using the simplified expression for $L_{n+1}$

$$ W_{n+1} = W_{n} + \frac{1}{L_{n+1}} = W_{n} + \frac{1}{\frac{A_{n} + 1}{W_{n}}} = W_{n} + \frac{W_{n}}{A_{n} + 1} $$

$$ W_{n+1} = \frac{W_{n}(A_{n} + 2)}{A_{n} + 1} $$

Taking the ratio of $L_{n+1}$ and $W_{n+1}$, we get the following expression:

$$ \frac{L_{n+1}}{W_{n+1}} = \frac{(A_{n} + 1)^{2}}{W_{n}^{2}(A_{n} + 2)} $$

At any iteration $n$, we add two rectangles with unit Areas to $R_{n}$, which means Area at iteration $n$ may be expressed as:

$$ A_{n} = A_{n-1} + 2 $$

which generates the following sequence of Areas at each iteration: $1, 3, 5, 7, 9, 11, 13, \dots, 2n - 1$ for all $n = 1, 2, 3, \dots, n$. Therefore, we may express $A_{n}$ as following:

$$ A_{n} = 2n - 1 $$

which makes $Equation (10)$ become:

$$ \frac{L_{n+1}}{W_{n+1}} = \frac{((2n - 1) + 1)^{2}}{W_{n}^{2}((2n - 1) + 2)} $$

$$ \frac{L_{n+1}}{W_{n+1}} = \frac{(2n)^{2}}{W_{n}^{2}(2n + 1)} = \frac{4n^{2}}{W_{n}^{2}(2n + 1)}$$

This relation is dependant on Area and Width of rectangle at $nth-iteration$. The width of rectangles as $n$ goes from $1, 2, 3, \dots$ is the following sequence which can also be observed in the above diagram: $1, \frac{3}{2}, \frac{15}{8}, \frac{35}{16}, \frac{315}{128}, \frac{693}{256}, \dots$ and if you make a quick google search by just writing the first $4$ terms of this sequence, it will show [this stackexchange link](https://math.stackexchange.com/questions/2992916/proving-that-these-two-finite-alternating-series-are-equal) among the top results. It seems an integral can be used to generate the reciprocal numbers of this series we have with us. The number sequence shown there is: $1, \frac{2}{3}, \frac{8}{15}, \frac{16}{35}, \frac{128}{315}, \frac{256}{693}, \dots$ The accepted answer points out at an expression as an integral for this sequence for given value of $n$ which is as following:

$$ \left[\int_{0}^{1} (1-x^{2})^{n} \; dx\right] $$

Notice that there are two difference between their sequence and ours. First, the table shown there is the reciprocal series of numbers that we have here as widths at each iteration starting from 1. This means the value of the above integral evaluated for any $n$ will be the multiplicative reciprocal of rectangle width at iteration $n$. Second, the sequence given there begins from $n = 0$ and we need it to start from $n = 1$ and give $W_{1} = 1$ which indicates that we will need to replace $n+1$ in place of $n$ in that expression. Compensating these changes in the above integral, we get the following expression for $W_{n}$:

$$ \frac{1}{W_{n}} = \left[\int_{0}^{1} (1-x^{2})^{n+1} \; dx\right] $$

Make another google search, this time ask for what integral of $(1-x^{2})^{n}$ is and you will get [the following stackexchange link](https://math.stackexchange.com/questions/2074881/how-to-integrate-this-function-int1-x2ndx) in the top searches. The accepted answer shows that when integrating from $-1$ to $1$, this integral evaluates to the following expression: 

$$ \left[\int_{-1}^{1} (1-x^{2})^{n} \; dx\right] = \frac{2(2n)!!}{(2n+1)!!} $$

Notice that the above integral function is even, i.e., with $x = -x$, it yields the same expression, which means it is symmetric about the y-axis. This means that integral evaluated from $0$ to $1$ is just half of this integral from $-1$ to $1$. Replacing $n$ with $n+1$ in $Equation (17)$ and multiplying by $\frac{1}{2}$, we get an expression similar to that in $Equation (16)$ which evaluates to:

$$ \frac{1}{W_{n}} = \frac{1}{2}\left[\int_{-1}^{1} (1-x^{2})^{n+1} \; dx\right] = \frac{(2(n+1))!!}{(2(n+1)+1)!!} = \frac{(2(n+1))!!}{(2n+3)!!} $$

The [double factorial](https://mathworld.wolfram.com/DoubleFactorial.html) of a non-negative integer $m$ is the product of all numbers from $1$ to $m$ that have the same parity (odd or even) as $m$. If $m$ is even, it can be expressed as $2k$ for positive integer values of k, then double factorial of $m$ may be expressed as:

$$ m!! = (2k)!! = 2^{k}k! $$

For an odd number $m$ which can be represented as $2k-1$ for positive integer values of $k$, we have:

$$ m!! = (2k-1)!! = \frac{(2k)!}{2^{k}k!} $$

Now observe that in $Equation (18)$, the term $2(n+1)$ in the numerator is even, while the denominator term $2n+3$ is odd. If we make these terms look like the above two expressions for even and odd values of $m$, we can write:

$$ (2(n+1))!! = 2^{n+1}(n+1)! $$

$$ (2n+3)!! = (2(n+2)-1)!! = \frac{(2(n+2))!}{2^{(n+2)}(n+2)!} $$

Putting these expressions back in $Equation (18)$, we get:

$$ \frac{1}{W_{n}} = \frac{(2(n+1))!!}{(2n+3)!!} = \frac{2^{n+1}(n+1)!}{\frac{(2(n+2))!}{2^{(n+2)}(n+2)!}} = \frac{2^{2n+3}(n+1)!*(n+2)!}{(2(n+2))!} $$ 

Bringing this expression for $\frac{1}{W_{n}}$ back to $Equation (14)$ gives us the following expression for Length to Width Ratio of $R_{n}$:

$$ \frac{L_{n+1}}{W_{n+1}} = (\frac{2^{2n+3}(n+1)!*(n+2)!}{(2(n+2))!})^{2} * \frac{4n^{2}}{(2n + 1)} $$

Now, let's try to evaluate this expression as $n$ approaches infinity. As $n$ grows very large, we can make some approximations that $n-3 \approx n+1 \approx n+2 \approx n$, and $2n+3 \approx 2n+1 \approx 2n$ but assume that $2(n+2) \approx 2n+1$ to bring the equation to a familiar form, which yields the following expression:

$$ \displaystyle \lim_{n \to \infty} \frac{L_{n+1}}{W_{n+1}} \approx (\frac{2^{2n}n!*n!}{(2n + 1)!})^{2} * \frac{4n^{2}}{2n} = (\frac{2^{2n}*(n!)^{2}}{(2n+1)!})^{2} * 2n $$

We take one power of $2^{n}$ from the numerator out to bring this expression to a cleaner form as following:

$$ \displaystyle \lim_{n \to \infty} \frac{L_{n+1}}{W_{n+1}} \approx 2n * (\frac{2^{n}*2^{n}*(n!)^{2}}{(2n)!})^{2} = 2n * 2^{2n} * ([\frac{2^{n}*(n!)^{2}}{(2n+1)!}])^{2} $$

At this point, you may want to make one last Google Search for the expression in the square bracket above which will again lead you to [math.stackexchange](https://math.stackexchange.com/questions/534915/limit-of-2n-n2-2n1) and you will see that via *Stirling's Approximation*, our bracket term *asymptotically approaches* the following expression:

$$ \frac{2^{n}*(n!)^{2}}{(2n+1)!} \sim \frac{\sqrt{\pi}}{2^{n+1}\sqrt{n}} $$

so we can reduce $Equation (26)$ with the above expression as following:

$$ \displaystyle \lim_{n \to \infty} \frac{L_{n+1}}{W_{n+1}} \approx 2n * 2^{2n} * (\frac{2^{n}*(n!)^{2}}{(2n+1)!})^{2} = 2n * 2^{2n} * (\frac{\sqrt{\pi}}{2^{n+1}\sqrt{n}})^{2} $$ 

$$ \displaystyle \lim_{n \to \infty} \frac{L_{n+1}}{W_{n+1}} \approx 2n * 2^{2n} * \frac{\pi}{2^{2n}*2^{2}*n} $$ 

Simplifying this expression, we get:

$$ \displaystyle \lim_{n \to \infty} \frac{L_{n+1}}{W_{n+1}} \approx \frac{\pi}{2} $$ 

<!-- This post will show up by default. To disable scheduling of future posts, edit `config.yml` and set `future: false`.  -->

Solution #2 (Closed Form Exact Solution)
------

We will start from $Equation (10)$ again.

$$ \frac{L_{n+1}}{W_{n+1}} = \frac{(A_{n} + 1)^{2}}{W_{n}^{2}(A_{n} + 2)} $$

Observe that $W_{n}^{2}$ may be written as the ratio of the product of length and width and ratio of length to width for rectangle $R_{n}$

$$ W_{n}^{2} = \frac{L_{n}W_{n}}{L_{n}/W_{n}} = \frac{A_{n}}{L_{n}/W_{n}} $$

Replace this expression back into $Equation (10)$ and we get the following relation for length to width ratio: 

$$ \frac{L_{n+1}}{W_{n+1}} = \frac{L_{n}}{W_{n}} * \frac{(A_{n} + 1)^{2}}{A_{n}(A_{n} + 2)} $$

Pay heed to this expression. It shows that the Length to Width ratio of rectangle $R_{n+1}$ is dependant on the Length to Width ratio of previous rectangle $R_{n}$ and its Area $A_{n}$. Since this relation is completely recursive and represents Ratio of $n+1$-th rectangle's dimensions in terms of previous rectangle's dimensions, we can do the same for Length to Width ratio of rectangle $R_{n}$ in this expression and rewrite it as following:

$$ \frac{L_{n+1}}{W_{n+1}} = [\frac{L_{n-1}}{W_{n-1}} * \frac{(A_{n-1} + 1)^{2}}{A_{n-1}(A_{n-1} + 2)}] * \frac{(A_{n} + 1)^{2}}{A_{n}(A_{n} + 2)} $$

Now if you open up $\frac{L_{n-1}}{W_{n-1}}$ using $Equation (33)$, and repeat, we get:

$$
\begin{align*}

& \frac{L_{n+1}}{W_{n+1}} = [\frac{L_{n-2}}{W_{n-2}} * \frac{(A_{n-2} + 1)^{2}}{A_{n-2}(A_{n-2} + 2)}] * \frac{(A_{n-1} + 1)^{2}}{A_{n-1}(A_{n-1} + 2)} * \frac{(A_{n} + 1)^{2}}{A_{n}(A_{n} + 2)} \\

& \frac{L_{n+1}}{W_{n+1}} = [\frac{L_{n-3}}{W_{n-3}} * \frac{(A_{n-3} + 1)^{2}}{A_{n-3}(A_{n-3} + 2)}] * \frac{(A_{n-2} + 1)^{2}}{A_{n-2}(A_{n-2} + 2)} * \frac{(A_{n-1} + 1)^{2}}{A_{n-1}(A_{n-1} + 2)} * \frac{(A_{n} + 1)^{2}}{A_{n}(A_{n} + 2)}

\end{align*}
$$

If we keep *uncoiling* this length to width ratio at the right side of this equation up to $n$-times, this ratio will finally boil down to $L_{1}/W_{1}$ which will be the following expression:

$$ \frac{L_{n+1}}{W_{n+1}} = \frac{L_{1}}{W_{1}} * \frac{(A_{1} + 1)^{2}}{A_{1}(A_{1} + 2)} * \frac{(A_{2} + 1)^{2}}{A_{2}(A_{2} + 2)} * \dots * \frac{(A_{n-1} + 1)^{2}}{A_{n-1}(A_{n-1} + 2)} * \frac{(A_{n} + 1)^{2}}{A_{n}(A_{n} + 2)} $$

Since $L_{1}/W_{1} = 1$, we may express the above expression as the following product:

$$ \displaystyle \frac{L_{n+1}}{W_{n+1}} = \prod_{k = 1}^{n} \frac{(A_{k} + 1)^{2}}{A_{k}(A_{k} + 2)} $$

Now from $Equation (12)$, we already know that $A_{k} = 2k - 1$, which makes the above expression become:

$$ \displaystyle \frac{L_{n+1}}{W_{n+1}} = \prod_{k = 1}^{n} \frac{((2k-1) + 1)^{2}}{(2k-1)((2k-1) + 2)} $$

$$ \displaystyle \frac{L_{n+1}}{W_{n+1}} = \prod_{k = 1}^{n} \frac{2k}{2k-1}*\frac{2k}{2k+1} $$

Finally, applying the limit as $n$ goes to infinity, we get the following expression:

$$ \displaystyle \lim_{n \to \infty} \frac{L_{n+1}}{W_{n+1}} = \prod_{k = 1}^{\infty} \frac{2k}{2k-1}*\frac{2k}{2k+1} $$

and if you make a quick Google Search, you will discover the above expression of the product is famously known as the *[Wallis Product](https://en.wikipedia.org/wiki/Wallis_product)* which is equal to:

$$ \prod_{k = 1}^{\infty} \frac{2k}{2k-1}*\frac{2k}{2k+1} = \frac{\pi}{2} $$

and hence, we conclude that:

$$ \displaystyle \lim_{n \to \infty} \frac{L_{n+1}}{W_{n+1}} = \frac{\pi}{2} $$

Verification
------

The following Python snippet calculates this limit using the relations for Length $L_{n}$ and Width $W_{n}$ described
in $Equations (4)$ and $(5)$. 

```python 
  def infinite_limit_of_ratio(n):
  L_n = 1; W_n = 1
  for _n in range(int(n)):
      # get Ln+1 and Wn+1
      L_np1 = L_n + 1./W_n
      W_np1 = W_n + 1./L_np1
      # print ratio after certain iterations
      if _n > 0 and _n % 100000 == 0:
          print(f"[n = {_n}] Ratio Ln+1/Wn+1 = {L_np1/W_np1}")
      # assign Ln+1 to Ln, Wn+1 to Wn to move on to next iteration
      L_n = L_np1
      W_n = W_np1
      pass
  pass

  # do 1 million iterations
  infinite_limit_of_ratio(n=1e6)
```

The following output log is produced at the output after each interval of 100k iterations.

```python 
  [n = 100000] Ratio Ln+1/Wn+1 = 1.5707923998679243
  [n = 200000] Ratio Ln+1/Wn+1 = 1.5707943633154777
  [n = 300000] Ratio Ln+1/Wn+1 = 1.5707950178050851
  [n = 400000] Ratio Ln+1/Wn+1 = 1.5707953450512318
  [n = 500000] Ratio Ln+1/Wn+1 = 1.5707955413993493
  [n = 600000] Ratio Ln+1/Wn+1 = 1.570795672298173
  [n = 700000] Ratio Ln+1/Wn+1 = 1.5707957657974314
  [n = 800000] Ratio Ln+1/Wn+1 = 1.57079583592197
  [n = 900000] Ratio Ln+1/Wn+1 = 1.5707958904632948

  Process finished with exit code 0
```


The length to width ratio approached within 1 million iterations is $\approx 1.5707958904632948$ and the actual value of $\pi/2 = 1.5707963267948966$ up to 16 decimal places which is quite close.