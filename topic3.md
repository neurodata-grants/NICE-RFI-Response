Topic 3: Learning:

Brains employ plasticity mechanisms that operate continuously and over multiple time scales to support online learning. Remarkably, brains continue to operate stably during ongoing plasticity.

For neuroscientists:
• What practical benefits could our current understanding of the brain's use of online learning over short and long time scales offer for next-generation computers? What gaps in understanding or challenges must first be overcome?
• Have there been simulations or demonstrations of how online learning over short and long time scales can be used to perform real-world tasks?

For computer scientists:
• What is the current state of research in the use of online learning over short and long time scales for digital or analog systems?
• Are there existing hardware systems that utilize online learning over short and long time scales? If so, in which application areas and use cases have these been deployed, and what are their performance characteristics?



Advances in optimization and signal processing for sensor data have focused on questions of learning parsimonious representations of signals, identification of salient information. How 
can we leverage structural data assumptions on phenomena to predict state using as little data as possible? How do we handle uncertainty in the structures or models we assume? What 
additional measurements should we collect in order to get the largest improvement to our accuracy? Some of the answers to these questions have been explored abstractly, assuming 
sparse, low-rank, and low-complexity parametric models, or with generic cost functions in online optimization and learning. However, many challenges remain before we may apply these 
techniques to realtime signal processing for learning systems, including handling time-varying phenomena and managing hierarchical data that arrive at different times and with 
different levels of uncertainty.

Consider two types of inference algorithms: online learning algorithms, which have optimization formulations and are deemed model-free, and estimation algorithms, which require 
knowledge of the uncertainty distribution. Contemporary online learning algorithms do not handle time-varying phenomena because of their lack of model inclusion, and classical online 
estimation algorithms are not robust to model misspecification. Recent work has sought to bridge this gap by introducing online learning with dynamics \cite{hall_online_2013, 
ledva2015inferring}, which uses collections of dynamical system models to develop estimates. This collection of models can be made up of different types of models of arbitrary form 
(\eg linear, nonlinear, time-varying), and the online learning algorithm simultaneously estimates state and selects the model or combination of models that best predicts the state at 
the next time step. The algorithm is based on mirror descent, one of the most current successful online optimization algorithms, and thus inherits many of its appealing properties. 
This hybrid approach is well-suited to our problem, in which we may need to represent at least a portion of the underlying system with dynamical system models (that we may learn over 
time), but those models may be complex and not suited for off-the-shelf estimation techniques like Kalman filtering.  Furthermore, we suspect that learning can be improved if we are 
allowed to manipulate the system to force it to explore states that it may otherwise have not, which is a natural technique humans have to learn in uncertain environments.

Online learning (or online optimization) algorithms \cite{nesterov1983method,nemirovsky1983problem} offer a way to optimize a cost function that can be decomposed in terms of each 
incoming data point. Stochastic optimization and incremental optimization are variants (and sometimes the various names are used interchangeably). The core advantage of online learning 
algorithms is their computational efficiency. Acceleration techniques beginning with \cite{nesterov1983method} have allowed us to guarantee fast convergence, and work such as 
\cite{nesterov2013gradient,beck2009fast} allows us to apply those to composite cost functions of a smooth cost (such as the $\ell_2$ norm) and a non-smooth regularizer (such as the 
$\ell_1$ norm). Examples of online learning algorithms include incremental or stochastic gradient, dual averaging, and mirror descent \cite{allen2014novel}.

Classically, an important drawback of online learning algorithms is that, while each iteration can be computed efficiently, they can require many more iterations in order to converge 
to the true solution. Beginning with \cite{nesterov1983method} and continuing to very recently, acceleration algorithms have been developed to guarantee that the number of iterations 
required for convergence is on the same order as allowed by second-order methods. These methods have proved to be so fast that the study of online learning has seen a resurgence of 
activity over the last five years with the application of mirror descent and acceleration methods to convex but non-smooth cost functions. This led to work on acceleration for 
composite cost functions made up of a smooth cost with a possibly non-smooth regularizer\cite{nesterov2013gradient,beck2009fast}.

Often processing big data requires the assumption of low-dimensional structure, such as sparsity or smoothness of the signal. A trusted approach to incorporate assumptions like this 
into our optimization problem uses a composite cost function made up of a smooth cost with a regularizer; this has many motivations including maximum likelihood for sparse noise 
models. However, regularizers that impose such structure are often non-smooth, and so it was only the acceleration methods of \cite{nesterov2013gradient,beck2009fast} that allowed us 
to accelerate first-order methods for these cost functions.

The analysis of these online methods is done in terms of the ``regret": the cumulative loss of the online algorithm as compared to another method, usually a batch method. This approach 
is very general and allows us to compare algorithms based on first the number of iterations they require to reach a certain error, and then the complexity per iteration. The techniques 
have been applied to many sparse and low-rank optimization problems where one wishes to decrease the per-iteration complexity by using first-order methods. This approach, as opposed to 
quantifying convergence to some true model or model parameters, can therefore be interpreted as a model-free version of filtering or online estimation.

In the case where the data do arise from a particular model, the batch method could be a consistent estimator. This estimator would come with a particular rate (in terms of number of 
data points required) of convergence to the true model parameters, and we could study whether the online method has the same rate. This is the classical technique of adaptive 
filtering: the classical techniques of Kalman filters, or least mean squares (LMS) and recursive least squares (RLS) techniques (\eg for subspace model tracking, see 
\cite{DelmasCardoso} for LMS and \cite{yang95} for RLS algorithms), are a special case.

Despite its obvious applicability, online learning has rarely been applied to problems where the data are streaming. One reason for this is that streaming data often measure 
time-varying phenomena, which precludes application of acceleration methods and typical online learning analysis. Some classical methods in adaptive filtering, Kalman filters being the 
prime example, were designed for a streaming time-varying context when the model dictating the temporal dynamics is known. In neural signal processing, we cannot expect the model to be 
known or easily parameterized.

The novel signal processing research we propose herein involves bridging this gap between classical filtering with known dynamics and generic optimization with time-invariance 
assumptions. The only work on this topic can be found in \cite{hall_online_2013, ledva2015inferring}. In the first work, two things are extended to the case of learning with dynamics: 
(1) the analytical online learning framework for working with data drawn from dynamical models, and (2) the mirror descent algorithm, which is central to the area of online learning; 
the extension is called Dynamic Mirror Descent (DMD). In the second work, DMD is applied to a problem in power systems where only aggregate measurements of the system are observed, and 
we must disaggregate the power contribution of different loads on the system. This will be analogous to several problems in neural processing where measured signals are the aggregation 
of many and yet the brain is still able to disentangle contributions from certain types of signals.

