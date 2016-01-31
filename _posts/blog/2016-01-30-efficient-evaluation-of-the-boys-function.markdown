---
layout: post
title: Efficient Evaluation of the Boys Function
modified:
categories: 
excerpt:
tags: []
image:
  feature:
date: 2016-01-30T13:33:00-05:00
---
A side project that I've recently been working (or trying to work) on is coding a fast molecular integral library in c. An important function in the calculation of coulombic integrals is the Boys function, $F_n(x)$. This function is given by:
$$ F_n(x) = \int_0^1 e^{-xt^2} t^{2n} dt $$

Evaluating this function frequently, accurately and quickly has been a focus of research for about the last half a century. I'll present a simple example here.

![plot1](plot1.png)

The evaluation of the Boys function can be broken into two cases, large $x$ values and small $x$ values.
# Large $x$ values:

For large x values the boys function can be approximated as:

$$F_n(x) = \int_0^1 e^{-xt^2} t^{2n} dt \approx \int_0^\infty e^{-xt^2} t^{2n} dt $$

This is related to the incomplete gamma integral and can be integrated giving:
$$F_n(x) \approx \frac{(2n-1)!!}{2^{n+1}} \sqrt{\frac{\pi}{x^{2n+1}}} \quad (x\ \mathrm{large})$$

![plot2](plot2.png)

# Small $x$ values:
To approximate the boys function for small $x$ values a Taylor expansion is employed:

$$F_n(x) = \sum_{k=0}^{\infty} \frac{(-x)^k}{k!(2n+2k+1)}$$

An infinite series is impractical in application (obviously) so this is truncated to six terms to achieve reasonable accuracy in reasonable time.

![plot3](plot3.png)

# Where does $x$ become large?

![plot4](plot4.png)

![plot4close](plot4close.png)

This is a question which has been bothering me, but for now I sidestepped the issue by returning the lowest value calculated by the two methods.

# Potential speed ups

![plot5](plot5.png)

* I'm calculating both expressions each time which is really bad
* I'm not implementing any recursion formulas

The later point is critical what I should be doing is calculating the Boys function at a very high order $n$ on a grid of $x$ points and using a downward recursion formula (upwards recursion is numerical unstable at smal $x$ values).

# References

1. [Molecular Electronic-Structure Theory](http://www.wiley.com/WileyCDA/WileyTitle/productCd-1118531477.html)
2. [Evaluation of the Boys Function using Analytical Relations](http://link.springer.com/article/10.1007/s10910-005-9023-3)
3. [A rigorous and optimized strategy for the evaluation of the Boys function kernel in molecular electronic structure theory](http://onlinelibrary.wiley.com/doi/10.1002/jcc.23935/abstract)
4. [ACE algorithm for the rapid evaluation of the electron-repulsion integral over Gaussian-type orbitals](http://onlinelibrary.wiley.com/doi/10.1002/(SICI\)1097-461X(1996\)59:3%3C209::AID-QUA4%3E3.0.CO;2-1/full?2-1/full)
