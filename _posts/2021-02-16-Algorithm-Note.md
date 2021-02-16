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

