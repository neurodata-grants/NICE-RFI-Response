Asynchronous computation has been commonly used to parallelize many data mining and machine learning algorithms.
Asynchronous computation removes computation barrier to reduce synchronization overhead in parallel environment.
It exposes the latest value of the local computation, which may help improve convergence in some applications
but may also waste computation and network bandwidth in some other applications. Maiter [2] formally defines
a set of graph algorithms that allows asynchronous computation and guarantees convergence. Some of the graph
algorithms such as PageRank and connected component detection may converge faster with asynchronous computation.
Many graph processing frameworks such as PowerGraph [3] and FlashGraph [4] support asynchronous computation to
accelerate computation if an algorithm allows.

[1] [Parallel and Distributed Computation:Numerical Methods](http://dspace.mit.edu/handle/1721.1/3719)
[2] [Maiter: An Asynchronous Graph Processing Framework for Delta-Based Accumulative Iterative Computation](http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=6600686&url=http%3A%2F%2Fieeexplore.ieee.org%2Fiel7%2F71%2F4359390%2F06600686.pdf%3Farnumber%3D6600686)
[3] PowerGraph
[4] FlashGraph
