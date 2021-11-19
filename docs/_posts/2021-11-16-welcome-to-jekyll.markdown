---
layout: post
title:  "Welcome to PaRange-STEllAR!"
date:   2021-11-16 11:53:13 -0600
categories: jekyll update
---
Welcome to PaRange-STE\|\|AR! A [STE\|\|AR Group](https://github.com/STEllAR-GROUP) initiative to dig into the C++20 ranges and evaluate their potential for parallelization.

STE\|\|AR Group develops [HPX](https://github.com/STEllAR-GROUP/hpx), a C++ Standard Library for Concurrency and Parallelism. Since HPX is both for Standard C++ and Parallelism, we only think it is proper that we investigate how the newly introduced ranges algorithms, would perform if parallelized. Along with ranges, the so called [views](https://ericniebler.github.io/range-v3/index.html#tutorial-views) were also introduced. This broadens the potential, given that various operation could now be chained with the `|` operator. Here is an example of the two options one might have when using C++ ranges:

{% highlight cpp %}
std::ranges::transform(vec, vec.begin(), [](auto i){return i * 2;});
std::ranges::for_each(vec, [](auto n){return 0;});
{% endhighlight %}

or

{% highlight cpp %}
std::for_each(std::ranges::views::transform([](int i)
  {return i * 2;}), [](auto n){return 0;});
{% endhighlight %}

What happens if we bring the C++ Standard Execution Policies into the conversation though?