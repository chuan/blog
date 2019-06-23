---
layout: post
title: Short Note on Linear Regression Implementations
---

Linear regression和相应的ridge regression是简单有效的统计模型。一般的实现都会吧feature normalize以后再计算相应的系数，得到结果以后可以再把结果换算成没有normalize之前的值。对于linear regression，怎么做关系不大。但是对于ridge regression这样和没有normalize直接计算weight得到的结果是不同的。

下面是引自statistical learning里面的话。

>The ridge solutions are not equivalent under scaling of the inputs, and so one normally standardizes the inputs before solving...

很多ridge regression的实现，有unscale的选项，但是它们的实际实现通常是把feature normalize，然后把计算得到的结果再除以之前normalize时用的scaling factor。这样的结果和完全不scale是不一样的。这是不是真的unscale呢？我认为有误导的嫌疑。