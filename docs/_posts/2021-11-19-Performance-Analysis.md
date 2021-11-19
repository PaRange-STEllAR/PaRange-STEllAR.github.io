layout: post
title: "Performance Analysis"
date: 2021-11-19
categories: PERFORMANCE


|               ns/op |                op/s |    err% |     total | benchmark
|--------------------:|--------------------:|--------:|----------:|:----------
|    1,147,832,361.00 |                0.87 |    4.8% |     12.08 | `reverse() then foreach()`
|      494,059,316.00 |                2.02 |    1.6% |      5.46 | `foreach(reverse view)`

|               ns/op |                op/s |    err% |     total | benchmark
|--------------------:|--------------------:|--------:|----------:|:----------
|      344,511,328.00 |                2.90 |    2.5% |      3.70 | `transform() then foreach()`
|      978,468,903.00 |                1.02 |    4.9% |     10.61 | `foreach(transform view)`