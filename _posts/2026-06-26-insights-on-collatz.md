---
layout: post
title: A Few Insights on Collatz Conjecture
excerpt: My sister and I have been working on a few topics in Number Theory, one of the topics is exploring the Collatz Conjecture. Here are a few insights.
mathjax: true
tags:
  - NumberTheory
  - CollatzConjecture
  - Math
---
My sister and I have been working on a few topics in Number Theory, one of the topics is exploring the Collatz Conjecture. Here are a few insights. 

Let's play a simple game. Choose any positive integer $n$ and follow these two steps:
- If n is **even**, divide it by two; $n → \frac{n}{2}$
- If n is **odd**, multiply it by three and add one; $n→3n+1$

Continue this process to generate a sequence of numbers.

Now, let us ask a few questions about the nature of this sequence and answer these questions through two lenses: *visual patterns* and *mathematical logic*.

First question -
## ***What does this sequence actually look like, and how does it behave?***

### Collatz's Tree and the Destination
If we test this rule with some values of $n$, we quickly see a pattern: the sequence, for any integer greater than 2, eventually goes to $4→2→1$ and ends up in a loop $4→2→1→4→2→1$.

This is the [**Collatz Conjecture**](https://en.wikipedia.org/wiki/Collatz_conjecture), one of the most famous unsolved problems in mathematics. In simple terms, it says that all numbers end up at 1 after a few transformations using the above rules.

In Figure 1, we can see that the spine contains all 2-adic numbers (the powers of 2). Any number of the form $2^{k}$ (where $k$ is a non-negative integer) travels a path along the spine. All other numbers, enter the spine eventually from one of the branches to reach the $4 → 2 → 1$ loop.

![Figure 1: The Collatz Conjecture Branch]({{ '/assets/images/fig1collatz.png' | relative_url }})
*Figure 1: The Collatz Conjecture Branch*

Another interesting observation about this figure is that the numbers branch at only the even exponents of 2 greater than 4. This can be proven using modular arithmetic. A branch arises at a number on the spine if there are multiple possibilities to reach that number. A default option is from the first rule $n → \frac n 2$. The other possibility is that it comes from $3n+1$, which we know is congruent to $1 \  mod \ 3$. So only if a number is congruent to $1 \  mod \ 3$, and the corresponding $n$ is odd, it can have a branch there. 

As 2 is congruent to $-1 \  mod \ 3$, any odd power of 2 is congruent to $(-1)^{odd}$ $=$ $-1$ (meaning it can be written as $3m-1$); any even exponent is congruent to $1 \  mod \ 3$. So, all even powers of 2 can be written as $2^{2k} = (3n+1)$ resulting in a branch there provided $n$ is an odd integer. By doing quick arithmetic, we can show that $n$ is always odd in this case. On the other hand $2^{2k+1}$ (odd exponents of 2) can not be written in the form $(3n+1)$ resulting in no branch at those numbers.

### Reverse Collatz's Tree
Let's now look at Figure 2 to understand different paths that numbers take to reach smaller numbers 1 to 9.  For example, a number will land up at 5, always through 10; and can reach 10 from either 3 or 20. Looking at this figure, we notice that all the multiples of 3 have a single path branch. This can be understood using the logic we discussed earlier. We can not obtain a number of the form $3k$ by applying the rule $3n+1$, so the only possible way to obtain it is from $6k$ and this logic continues.


![Figure 2: Reverse Collatz Tree]({{ '/assets/images/fig2collatz.png' | relative_url }})
*Figure 2: Reverse Collatz Tree*

Writing this sequence for a few numbers, we realize that the sequence hits a maximum somewhere before collapsing to 1 (in some cases the maximum number in the sequence is the number itself). 


This leads us to our next question:
## ***How does the maximum value of sequence change as $n$ increases, and is it unique for each $n$?***
### Behavior of maximum value of a sequence

Let’s see how different starting numbers behave by looking at three consecutive integers: 26, 27, and 28. *(we will stop writing the sequence once it hits 1, right before it enters in the $4→2→1$ loop)*

$n = 26$:
$26 → 13 → 40 → 20 → 10 → 5 → 16 → 8 → 4 → 2 → 1$ 

$n = 27$:
27 reaches a maximum value of 9232 in the sequence before climbing down. It has a total steps 111 in the sequence before hitting 1 for the first time.

$n = 28$:
$28 → 14 → 7 → 22 → 11 → 34 → 17 → 52 → 26 → 13 → 40 → 20 → 10 → 5 → 16 → 8 → 4 → 2 → 1$

Now let's look at the first chart ("Max Values Reached $(3n+1)$") in Figure 3, where we plotted Max Value vs Branch Starting Number with y-axis in log scale. When we plot the *maximum value* for a range of numbers (in this case from 1 to 10,000), we notice that the *maximum values* are all over the place. Some hit very high values, and at the same time we notice a clear lower bound for max values. This linear-looking lower bound, $y = x$, can be explained by:
- For any $n$, the maximum value of the sequence can not be less than $n$ (as $n$ is a part of the sequence). Hence maximum values must lie in the region $y >= x$.
- When $n$ is an even of the form $2^k$, the number itself is the max value, i.e., maximum value lies on $y = x$.
- For all other values of $n$, the maximum value will lie above $y = x$ line.


![Figure 3: Collatz Conjecture Analysis]({{ '/assets/images/fig3collatz.png' | relative_url }})
*Figure 3: Collatz Conjecture Analysis*
### Total iterations (or steps) before reaching 1
Looking at the "Total Iteration Steps Before Reaching a Loop" chart in Figure 3, we do not notice any clear trend in total number of steps as $n$ increases. But a closer look at the chart shows some exponential parallel wave-like patterns. This has to do with the spine and the branches we touched earlier. We will have a deep dive into this pattern in separate blogs.

Now let's look at another question,
## What is special about 3 in $3n+1$? Why does this sequence always reach 1? Is this the case if we replace 3 with some other odd integer?

**Before we start, let's reframe the rules:**
Choose any positive integer $n$ and follow these two steps:
- If n is **even**, divide it by two; $n → \frac{n}{2}$
- If n is **odd**, multiply it by $k$ and add one; $n→kn+1$; where $k$ is an odd positive integer
Continue this process to generate a sequence of numbers until it reaches 1 or hits an infinite local loop (other than one). Also, we stopped if we had a strong evidence that the sequence was heading to infinity.

#### Case 1: $k = 1$  ($n→n+1$ transformation when $n$ is *odd*)
So we will apply the following rules:
- If $n$ is **even**, divide it by 2; $n → \frac n 2$
- If $n$ is **odd**, add 1 to it; $n → n+1$

Figure 4 captures various graphs for this case. 


![Figure 4: $(n+1)$ Variant]({{ '/assets/images/fig4collatz.png' | relative_url }})
*Figure 4: $(n+1)$ Variant*

**Key Observations:**
- We can see that again, the sequence falls to 1, and then enters a loop - this time it is $2 → 1$. We can mathematically prove that this sequence always collapses to 1.

- If $n$ is odd, the next step gives us $n+1$, which is even. In the following step, we divide by 2, so we get $\frac{n+1}{2}$. If we skip the intermediate step, the odd transition is essentially $n→\frac{n+1}{2}$​. For any integer $n>1$, we have $\frac{n+1​}{2} < n$, which means the number is reducing. 

- Similarly, if $n$ is even, we get $\frac n 2$ in the next step which is less than n, so again it is reducing. This means the sequence is on a downward spiral. 

- For any sequence, we have three options - go to infinity, reduce to 1 and get into a loop, or get into a local loop (other than 1). From the above argument, it can not go to infinity. If it had to enter a local loop (that is, a loop other than 1), then one of the numbers in the sequence should have already appeared in the sequence. But, as the sequence is decreasing, this is not possible either. So the only option left is that it will come down to 1 (and loop $1 → 2 → 1$).

- We do not see crazy variation in the maximum values as we did in case of the Collatz Conjecture.

- For the lower bound of maximum value (from Max Value vs Branch Starting Number with y-axis in log scale), the same logic of $(3n+1)$ holds true here as well.

- Total iteration steps for any $n$ in a given range is less for $(n+1)$ case compared to the Collatz Conjecture.

#### Case 2: $k = 5$  ($n→5n+1$ Transformation when $n$ is *odd*)
So we will apply the following rules:
- If $n$ is **even**, divide it by 2; $n → \frac n 2$
- If $n$ is **odd**, add 1 to it; $n → 5n+1$

Figure 5 captures various graphs for this case. 

![Figure 5: $(5n+1)$ Variant]({{ '/assets/images/fig5collatz.png' | relative_url }})
*Figure 5: $(5n+1)$ Variant*

We notice that the behavior changes drastically in this case. In Figure 5, we see that there are some red squares for "Min Value Reached vs Branch Starting Number". These are the points where the sequence gets into local loops (loops which don't reach 1). A few interesting observations are:
- We see a few clear levels for max value ("Max Values Reached $(5n+1$)$"), with quite a few numbers getting into local loops.
- In the plot of "Total Iteration Steps Before Reaching a Loop vs Branch Starting Number", we see two interesting trends - one for the numbers that don't get into any local loops, and another for those getting into local loops (clearly marked by the red dots). We will explore this more later.
- We also see a few distinct levels for minimum value (other than 1). Notice that minimum value =1 plot looks continuous line due to crowding of dense dots. The number of integers that get into a local loop (other than at 1) are far lesser compared to those that reach 1. Figure 6 is the same plot with smaller range (1-100) to give a better idea about this behavior.

![Figure 6: $(5n+1)$ Variant with a Smaller Range]({{ '/assets/images/fig6collatz.png' | relative_url }})
*Figure 6: $(5n+1)$ Variant with a Smaller Range*

## Why the Collatz Conjecture Matters

This brings us back to the special $3n+1$ rule of the Collatz Conjecture. It's not just a random puzzle. We see similar patterns at seemingly unrelated areas. It seems to have interesting applications in fields like cryptography and pseudo-random number generation. 

Also, attempts to prove this conjecture is not just for intellectual satisfaction. Some of the tools developed as part of these attempts can help in solving many real-world problems.

---
