---
layout: post
title: Algorithm Analysis
---

<p>From my experience, usually, only two algorithm analysis techniques are tought in college level algorithm analysis classes: asymptotic analysis and amortized analysis. There are some addtional analysis frameworks or tools that can reveal or explain other interesting aspects of certain algorithms and data structures. Here are three interesting examples.</p>

<p><b><a href="http://en.wikipedia.org/wiki/Competitive_analysis_(online_algorithm)" title="Competitive analysis">Competitive analysis</a></b><br />
I think the best introduction to this line of analysis is still Sleator and Tarjan's 1985 paper, "<a href="http://www.cs.cmu.edu/~sleator/papers/amortized-efficiency.pdf" title="Amortized efficiency of list update and paging rules">Amortized efficiency of list update and paging rules</a>." It reveals why a simple list update operation can be as competitive as an optimally designed algorithm that knew the data it operates on in advance. The analysis is simple yet surprising. The paper alone is worth reading for pleasure if you did not know it before.</p>

<p><b><a href="https://www.worldscibooks.com/compsci/n111.html" title="Algorithms and data structures for external memory">External memory</a></b><br />
RDBMS is the most popular data management system in the past three decases. To my knowledge, every RDBMS includes some kind of B-tree implementation. The external memeory analysis shows why algorithms and data structures like B-tree operate so well in the world of layered storage systems. In other words, if you data does not fit into memory, you may want to use this model to analysis and design your algorithms that need to access data outside memory.</p>

<p><b><a href="http://en.wikipedia.org/wiki/Smoothed_analysis" title="Smoothed analysis">Smoothed analysis</a></b><br />
Simplex method is a popular algorithm to solve linear programming problems. It has a exponential time worst case according to asymptotic analysis. However in practice, it works very well. The smoothes analysis offered an theoritical explanation of the phenomena.</p>

<p>The three examples above are interesting for me. After I graduated from college and began to work in the industry, there are times I found the code used in practice was quite different than what I thought and wrote in college. When choices of data structures and algorithms need to be made for problems, there are places algorithms with worse big Os are used, and simple and straight forward data structures are favored over sophisticated ones that may prove better on paper. However, when I look deeper and analysis in the exact context of the problem, many times those choices begin to make sense. The three examples above always reminded me when considering an algorithm and data structure for a real problem, there are usually more things need to be taken into account than simple big O notations. I think this is also the reason we still need to do simulations and experiments when we choose or design algorithms and data structures, at least for many real world problems.</p>