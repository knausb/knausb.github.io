---
title: Getting started with Rcpp
author: Brian J. Knaus
date: '2018-06-14'
slug: getting-started-with-rcpp
categories: [R, Rcpp]
tags: [R, Rcpp]
description: 'Getting started with Rcpp'
---

A colleague recently asked about getting started using Rcpp.
After I sent the e-mail I thought that information may be of use to others.
So I decided to blog about it.

[Rcpp](http://www.rcpp.org) is [a package on CRAN](https://cran.r-project.org/web/packages/Rcpp/index.html) that facilitates an interface between R and C++.
It includes data structures that allow for easy sharing of data between the two languages.
Because writting C++ code is usually more challenging than writing R code you should probably reserve it for tasks that you will repeat.
And if you're going to repeat them you might as well put them in a package.
I've put together my own version of a package skeleton that I use and you can find it [here](https://github.com/knausb/myRPkg).

Once you have a package set up you'll need to learn how to add code to it.
Hadley Wickham has a nice introduction in his [book on R packages](http://r-pkgs.had.co.nz/src.html) and his [book on advanced R](http://adv-r.had.co.nz/Rcpp.html). There is also the [Rcpp Gallery](http://gallery.rcpp.org).
If you need some helpgetting started with C++ you might try their tutorial at [cplusplus.com](http://www.cplusplus.com/doc/tutorial/).
And of course, there are our good friends Google and stackoverflow.

**Compilers**, oh yes, did I mention compilers?
If you are working in a *nix environment (except OSX) you probably already have a compiler, usually gcc, so you should be good to go.
If you are working on a Mac, you'll need [Xcode](https://developer.apple.com/xcode/) which includes clang.
And if you're working in Windows, you'll need [Rtools](https://cran.r-project.org/bin/windows/Rtools/).

Once you're up and running you might notice that there is something wrong with your code.
Don't feel bad, it happens to all of us!
You'll need to debug it.
A simplistic way of dealing with this is to write to stdout at various points in your code.

```
Rcpp::Rcout << "We made it this far in the code!" << std::endl;
```

For something a little more sophisticated, Kevin Ushey has some nice posts on using debuggers with Rcpp such as [valgrind](http://kevinushey.github.io/blog/2015/04/05/debugging-with-valgrind/) and [lldb](http://kevinushey.github.io/blog/2015/04/13/debugging-with-lldb/), which is similar to gdb.

Those are the links I've used, and reused, to help myself learn Rcpp and C++.
Have fun with compiled code in R!
