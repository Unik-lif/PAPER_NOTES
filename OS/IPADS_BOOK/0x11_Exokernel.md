## 概要：
外核的设计主要还是为了让应用程序能够特质化地访问部分硬件资源，实现`VM`和`IPC`的自行管理。
## Gap：
作者认为操作系统提供的抽象虽然很有用，但是却限制了应用的很多自由度，明明他们针对不同场景可以有相当程度上的优化，但如果添加了OS这一层抽象层无疑像是带着镣铐跳舞。

外核的建立基于一个基本的观察，对应的抽象层越低，则其能够发挥的功效、运转的纬度更为丰富，功能也会更加强大。

当前如果抽象过于固定或者高，会让应用程序为了达到相同的运行速度，不得不写的更加复杂，穷尽努力去把工作做好。不仅有效率和性能上的问题，其实也有安全与可维护性上的问题。

外核由一个外核本身，以及上层的`libOS`共同组成。应用程序通过调用不同的`libOS`所对应的服务，来自定义地挑选更符合自身需求的一些和硬件更紧密联系的特性。

有点好奇参考ExoKernel是否有其他的一些工作出来，最好比较系统，以及有一些代码，可以学到更多的知识。

很难说有没有启发`dune`之类的工作。