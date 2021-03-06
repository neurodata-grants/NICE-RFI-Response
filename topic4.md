Topic 4: Co-local memory storage and computation:
* What is the current state of research in the use of co-local memory storage and computation for digital or analog computing systems?
* Are there existing hardware systems that utilize co-local memory storage and computation? If so, in which application areas and use cases have these been deployed, and what are their performance characteristics?

Data transferring is usually the bottleneck of data-centric
computation systems. As the advance of processors, the speed gap
between processors and memory storage continues increasing.
Collocating memory storage and computation helps to avoid data
transferring from being the bottleneck.

At a small scale, there are attempts of co-locating computation in
disks or RAM to achieve better energy efficiency and reduce data
traffic to improve performance. For example, ActiveDisk [1, 2]
utilizes on-drive processors to perform some portions of application
computation to exploit larger internal memory bandwidth, significantly
reduce data traffic and improve performance of some data mining tasks.
Nanostores [3], on the other hand, exploits another approach that
designs a single chip with both non-volatile memory and
energy-efficient compute cores. This design achieves a much more
energy-efficient systems for many large-scale data analysis tasks.
Similarly, IRAM [4] was an attempt of integrating processors and RAM
in the same chip to increase memory bandwidth and improve energy
efficiency.

At a large scale, the same principle is applied to large-scale data
analysis in commercial data centers. Unlike supercomputers that have
separate computation nodes and storage nodes, each node in a
commercial data center plays the role of computation and storage.
Large-scale data analysis systems such as Hadoop take advantage of
this system design and assigns computation to the node where data
resides. This strategy significantly reduces data transmission between
nodes in a cluster and allows the software systems to scale to very
large clusters with commodity hardware.


[1] [Active Disks for Large-Scale Data Processing](http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=928624)

[2] [Active disk meets flash: a case for intelligent SSDs](http://dl.acm.org/citation.cfm?id=2465003)

[3] [From Microprocessors to Nanostores: Rethinking Data-Centric Systems](http://www.hpl.hp.com/news/2011_IEEEComputer_nanostores.pdf)

[4] [A case for intelligent RAM](http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=592312)
