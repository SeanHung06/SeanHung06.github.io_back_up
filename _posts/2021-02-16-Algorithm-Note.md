---
layout: post
title: Algorithms-Divide-Conquer
description: Algorithms-divide-conquer/lecture --merge-sort-analysis
categories: jekyll update

---

**[Coursera/Algorithms](https://www.coursera.org/learn/algorithms-divide-conquer/lecture/wW9On/merge-sort-analysis)**



    Note while Learning Algorithms-Divide-Conquer in Coursera

### Merge-Sort:

* Running Time for Merge Sort 
* Claim : For every Input array of n numbers                     
Merge Sort produce a sorted array and uses at most 6nlog2n + 6n operations

* Persuedo Code 
{% highlight ruby %}
    for k =1 to n :
        if A[i] < B[j] :
            C[k]=A[i]
            i++
        else B[j] < A[i] :
            C[k]=B[j]
            j++
    end
{% endhighlight %}

`Proof of Claim`

At each Level j = 0,1,2..... , log2n , there are 2^j subproblems and , each of size n/2^j
* Total of operations at level j <= 2^j * 6 * (n/2^j)        
`[6 indicates that every merge subroutine at most 6 operations]`
 
**->** 6n     `[Independent J levels]`
 
**->** 6n * (log2n+1)      `[All Levels] Plus one Because of 0 Level`

`The screen shot for Insertion-Sort and Merge-Sort Time Complexity Chart--Rate of growth for Large problem size`
![My helpful screenshot](/assets/Insertion_Sort_Merge_Sort.png)


### Asymptotic Analysis
* High Level Idea : Suppress constant Factors and lower-order terms 
* Example : 6nlog2n+6n with just nlogn
* Terminology : Running time isd O(nLogn) [Big - Oh of n logn]


`Big O Basic Examples of Proof`
* The notation Ο(n) is the formal way to express the upper bound of an algorithm's running time.  
It measures the worst case time complexity or the longest amount of time an algorithm can possibly take to complete.


* Claim : 
{% highlight ruby %}
    If T(n) = Akn^k+.....A1n+A0
        Then 
            T(n) = O(n^k)
{% endhighlight %}
* Proof:
{% highlight ruby %}
    Choose n0 = 1 and c = |Ak|+|Ak+1|+.....|A1|+|A0|
        T(n) <= Akn^k+.....A1n+A0
        T(n) <= Akn^k+.....|A1|n^k+|A0|n^k
        T(n) <= C*n^k
{% endhighlight %}

`Omega Notation`
* The notation Ω(n) is the formal way to express the lower bound of an algorithm's running time.     
It measures the best case time complexity or the best amount of time an algorithm can possibly take to complete.

{% highlight ruby %}
T(n) = Ω(f(n)) 
if and only if given two Constants C,n0 such that T(n) >= c.f(n) 
for all n > n0. 
{% endhighlight %}
![My helpful screenshot](/assets/Omega_Notation.png)

`Theta Notation`
* The notation θ(n) is the formal way to express both the lower bound and the upper bound of an algorithm's running time.     
{% highlight ruby %}
T(n) = θ(f(n)) 
if and only if T(n) = O(f(n)) and T(n) = Ω(f(n))
for all Constants c1,c2,n0 such that 
c1(f(n))< T(n) < c2(f(n)
for all n > n0. 
{% endhighlight %}

![My helpful screenshot](/assets/theta_notation.jpg)

`Little O Notation`
* The notation Ω(n) is the formal way to express the lower bound of an algorithm's running time.     
It measures the best case time complexity or the best amount of time an algorithm can possibly take to complete.

{% highlight ruby %}
T(n) = o(f(n)) 
if and only if given two Constants C,n0 such that T(n) <= c.f(n) 
for all n > n0. 
{% endhighlight %}

* For all k>=1 , n^k-1 = o(n^k)




### Assignment 1

In this programming assignment you will implement one or more of the integer multiplication algorithms described in lecture.

To get the most out of this assignment, your program should restrict itself to multiplying only pairs of single-digit numbers.  
You can implement the grade-school algorithm if you want, but to get the most out of the assignment 
you'll want to implement recursive integer multiplication and/or Karatsuba's algorithm.

So: what's the product of the following two 64-digit numbers?

3141592653589793238462643383279502884197169399375105820974944592

2718281828459045235360287471352662497757247093699959574966967627

{% highlight ruby %}
# Python 2 and 3
def karatsuba(num1, num2):
    num1Str, num2Str = str(num1), str(num2)

    if num1Str[0] == '-': return -karatsuba(-num1, num2)
    if num2Str[0] == '-': return -karatsuba(num1, -num2)

    if num1 < 10 or num2 < 10: return num1 * num2
    
    #retreive the split position
    maxLength = max(len(num1Str), len(num2Str))
    splitposition = maxLength //2 
    
    highX = int(num1Str[:-splitposition])
    lowX = int(num1Str[-splitposition:])
    highY = int(num2Str[:-splitposition])
    lowY = int(num2Str[-splitposition:])
    
    a1 = karatsuba(highX,highY)
    d1 = karatsuba(lowX,lowY)
    e1 = karatsuba((highX+lowX),(highY+lowY))-a1-d1
    
    
    return (a1*10**(splitposition*2))+(e1*10**(splitposition))+d1

{% endhighlight %}



[TIP: before submitting, first test the correctness of your program on some small test cases of your own devising. 
Then post your best test cases to the discussion forums to help your fellow students!]

[Food for thought: the number of digits in each input number is a power of 2.  
Does this make your life easier?  
Does it depend on which algorithm you're implementing?]

The numeric answer should be typed in the space below.  
So if your answer is 1198233847, then just type 1198233847 in the space provided without any space / commas / any other punctuation marks.    
(We do not require you to submit your code, so feel free to use any programming language you want 
---just type the final numeric answer in the following space.)

