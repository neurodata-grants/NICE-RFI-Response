For computer scientists: 

- What is the current state of research in the use of asynchronous computation and/or transient coordination for digital or analog computing systems? 
- Are there existing hardware systems that utilize asynchronous computation and/or transient coordination? If so, in which application areas and use cases have these been deployed, and what are their performance characteristics?

Asynchronous computation has been commonly used to parallelize many data mining and machine learning algorithms.
In the context of parallel computing, asynchronous computation removes computation barrier to reduce synchronization
overhead and increase parallelism to speed up computation. By exposing the latest value of the local computation,
it may even accelerate convergence in some applications.

In the case of graph analysis, there are a large set of graph algorithms that allows
asynchronous computation and guarantees convergence, as defined by Maiter [2]. Some of the graph
algorithms such as PageRank and connected component detection converges even faster with asynchronous computation.
Many graph processing frameworks such as PowerGraph [3] and FlashGraph [4] support asynchronous computation to
accelerate computation if an algorithm allows.

Another example of asynchronous computation is gradient descent.
When we apply gradient descent to some optimization problems, we can update the training parameters asynchronously
and in a lock-free fashion, if the models are sparse [5] or if the updates are associative and commutative [6].
In both cases, the asynchronous update still guarantees convergence [7].

Gradient descent is a workhorse of online algorithms and deep learning networks. 
Therefore since gradient updates can be performed in parallel asynchronously, the speedups in these 
important learning problems will be nearly linear with the number of computational elements. 


[1] [Parallel and Distributed Computation:Numerical Methods](http://dspace.mit.edu/handle/1721.1/3719)

[2] [Maiter: An Asynchronous Graph Processing Framework for Delta-Based Accumulative Iterative Computation](http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=6600686&url=http%3A%2F%2Fieeexplore.ieee.org%2Fiel7%2F71%2F4359390%2F06600686.pdf%3Farnumber%3D6600686)

[3] [PowerGraph: Distributed Graph-Parallel Computation on Natural Graphs](https://www.usenix.org/conference/osdi12/technical-sessions/presentation/gonzalez)

[4] [FlashGraph: Processing Billion-Node Graphs on an Array of Commodity SSDs](https://www.usenix.org/system/files/conference/fast15/fast15-paper-zheng.pdf)

[5] [HOGWILD!: A Lock-Free Approach to Parallelizing Stochastic Gradient Descent](http://machinelearning.wustl.edu/mlpapers/paper_files/NIPS2011_0485.pdf)

[6] [Project Adam: Building an Efficient and Scalable Deep Learning Training System](http://www.cs.otago.ac.nz/cosc440/readings/osdi14-paper-chilimbi.pdf)

[7] Z. Peng, Y. Xu, M. Yan, and W. Yin, ARock: an Algorithmic Framework for Asynchronous Parallel Coordinate Updates, UCLA CAM Report 15-37, 2015. 
