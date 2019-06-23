---
layout: post
title: HFT Seminar
---

今天上午听了<a href="http://www.cs.jhu.edu/seminars/2010/spring/may6/niall-dalton">一场关于HFT的seminar</a>。HFT在美国流行到什么程度呢？今天听说超过60%的交易量都是来自HFT。其中大约一半是投资银行和造市商，一半是独立机构。时间很少，而且因为牵涉到商业机密，很多具体的地方都语焉不详。我的有几点印象。可能不准确的地方也很多。

1. 交易系统本身架构很简单。
	* 输入是交易数据。也有公司利用新闻数据，不过会复杂很多。
	* 第一层处理是把数据转换成自己的格式。
	* 处理完之后计算模型在一个系统。这个系统是一个整体。包括了交易模型、风险控制、自动下单等等。没有多层layer。他提了很多次，多层架构对他们没有意义。
	* 在HTF领域，模型相对简单。时间复杂度可能只有线性。</li>
	* 这个系统本身的数据库是一个自己写的in memory database。（这种似乎很常见：Bloomberg说他们的新闻处理也是自己写的in memory database。）
	* 他后来演示了一下这个数据库，binary大概500k左右，代码180k lines左右。不是SQL。用的是自己的数据处理语言。据说快很多。（这个我表示怀疑。）
2. 套利模式主要是利用计算机的速度。和交易的规模。
3. 每天清仓。他给的数字好像是每天不超过30million$。
4. 他们要考虑到网络延迟。比如从chicago过来的光纤比纽约要慢10ms，欧洲可能要x10。
5. 当他们的交易量足够大的时候，证交所或者造市商还要向他们付钱。（我的理解是因为他们提供了流动性。）
6. 第三方提供的接口和数据很不干净。（包括.net, java, c, etc.）
7. 他们的系统从接到数据，到计算出结果比数据和交易的latency还要快。他给的时间好像是20纳秒。
8. 但是第三方交易系统的处理能力往往不够，所以他们的系统要把对方的处理能力也考虑进去。
9. 这个演讲的人比我想的要聪明。中间有人提问他们用不用GPU。他大概讲了一下为什么GPU的计算模型不适用。分析很到位。之前的数据库也是一个人写出来的。
10. 他们还写自己的java compiler，以及很多自己in house的技术和工具，包括前面的数据库。
11. 他们招人的时候主要看这个人懂不懂一个程序在电脑里是怎么运行的。每一行程序对memory，cache，CPU的影响。
23. 测试、容错等等也是难题。

听的过程中一个感觉就是交易所的交易系统似乎非常繁复杂乱，像个菜市场，安全也没有保证。处理这么多的钱的系统，让我觉得有点儿戏。听完以后回来，结果不久道琼斯就因为某错误交易暴跌1000点。

再加一些个人意见：刚才看了一下<a href="http://www.linkedin.com/in/nialldalton">演讲人的Linkedin资料</a>。他之前在Nvidia做过software engineer。这可能解释了为什么他对GPU计算理解的准确性。他之前工作的另一个公司<a href="http://kx.com/">Kx System</a>也很有意思。这个公司的主要产品就是一个in memory database - kdb，而且它的处理语言也挺有意思：<a href="http://en.wikipedia.org/wiki/K_programming_language">k programming language</a>。我虽然没有用过，但是就描述上，这个数据库就和之前他演示的数据库非常像。


<strong>Update:</strong> 《60 minutes 》最近有一个关于HTF的报道。他们的标题体是speed traders，以快取胜也是我的感觉，与其说是高频交易，不如说是自动快速交易。

<a href="http://www.cbsnews.com/video/watch/?id=7368460n">http://www.cbsnews.com/video/watch/?id=7368460n</a>

</div>