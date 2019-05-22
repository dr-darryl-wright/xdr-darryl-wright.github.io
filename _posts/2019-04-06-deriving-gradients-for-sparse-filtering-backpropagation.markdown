---
layout: post
title:  "Deriving Sparse Filtering Gradients with the Backpropagation Idea"
date:   2019-04-06 11:31:47 -0500
categories: derivations
mathjax: true
---
During my PhD I used [Sparse Filtering][ngiam11] as part of a classifier for the [Pan-STARRS1][ps1]
Survey for Transients ([PSST][psst]) to predict whether detections are real (e.g. supernovae) or bogus (due to electronic artefacts for example).  The classifier produces the RB Factor (real-bogus factor) that can be seen [here][rbfactor].  The paper presenting Sparse Filtering provides a link to [example code][code], however it was not transparent to me how the backpropagation steps there were derived.

Below is the derivation of the gradients for sparse filtering backpropagation using the [backpropagation idea][backprop].

Sparse filtering is an *unsupervised feature
  learning* method.  Unsupervised feature
  learning is employed to learn high-level features from
readily available unlabelled data and has been shown to learn
object-selective features (see [Coates et a. 2011][coates2011] for details).  An unsupervised learning
algorithm takes as input an unlabelled training set $$X$$ and outputs a
function, $$f$$ that maps the
$$n$$-dimensional feature vector $$x^{(i)}$$ to a new $$K$$-dimensional feature
representation ($$f : \mathbb{R}^n \to \mathbb{R}^K$$).  For the supervised
learning task the labelled training examples are then mapped to the
new representation.  This is typically done by comparing each training
example to each of the $$K$$ learned features and calculating a
similarity or *activation* for how much that feature represents
the training example, producing a $$K$$-dimensional representation of activations.

In order for the learned high level features to be useful, there are
some properties that we desire from the feature distribution.  The
first is known as *population sparsity* ([Willmore & Tolhurst 2001][willmore2001], [Ngiam et al. 2011][ngiam11]), where each training example
is only represented by a few active (i.e. non-zero) features.  This
helps ensure that the learned features are informative; only a few
should be required to describe each example.

The second desirable attribute is *lifetime sparsity*
([Willmore & Tolhurst 2001][willmore2001], [Ngiam et al. 2011][ngiam11]).  Each feature should only be active for a few
training examples.  The idea here is that features should be
discriminative and avoid the situation where some features are active
(or inactive) for all training examples.  Such features provide no information to
distinguish between targets.  These are the kinds of heuristics we must rely upon and optimise for
during unsupervised learning, where there is no clear performance metric.

The main advantage of sparse filtering over other algorithms is the number of hyperparameters which need to be selected.  In practice choosing hyperparameters requires cross-validation which is computationally expensive scaling exponentially with the number of hyperparameters.  Sparse filtering has only one hyperparameter $$K$$, the number of features to learn.  This in itself is an advantage, but given that sparsity implies learning a large number of features we could simply set this to be as large as we could reasonably compute with out worrying about cross-validation, although there are likely diminishing returns.

To get started with the derivation, forward porpagation begins with the soft-absolute function that learns linear features for every
training example.

$$
\begin{equation}
a_j^{(i)} =\sqrt{(\textbf{W}_j^T\textbf{x}^{(i)})^2+\epsilon}\
\approx\ 
|\textbf{W}_j^T\textbf{x}^{(i)}|\tag{1}\label{eq:one},
\end{equation}
$$

where $$a_j^{(i)}$$ represents the $$j$$-th activation for the $$i$$-th
training example.  If we wish to learn $$K$$ features from our
$$n\times1$$ input examples, then $$\textbf{W}$$
will be a $$n\times K$$ matrix.  We can think of $$\textbf{W}$$ as
storing $$K$$ $$n$$-dimensional learned features.  Sparse filtering attempts to update $$\textbf{W}$$ such
that these features are optimised for population and
lifetime sparsity.

We begin by randomly intialising $$\textbf{W}$$.  During each iteration of
sparse filtering for each training example we calculate it's
activation with respect to each of the features stored in $$\textbf{W}$$.
The activations are then constrained to lie
on the unit $$\ell_2$$-ball in $$\mathbb{R}^{K}$$.  To achieve this
we first normalise the activations such that the sum of activations
across the training examples is equal by dividing by its $$\ell_2$$-norm

$$
\tilde{\textbf{a}}_j =
\textbf{a}_j/\left|\left|\textbf{a}_j\right|\right|^{}_2\tag{2}\label{eq:two}.
$$

The result is then normalised across each training example so they lie
on the unit $$\ell_2$$-ball

$$
\hat{\textbf{a}}_j = \tilde{\textbf{a}}_j/\left|\left|\tilde{\textbf{a}}_j\right|\right|^{}_2\tag{3}\label{eq:three}.
$$  

The result of these transformations is then
optimised for sparsity by the $$\ell_1$$ penalty.  The sparse filtering objective 
function to minimise is then

$$
J(\textbf{W}) = \sum_{i=1}^m\left|\left|\ \hat{\textbf{a}}^{(i)}\right|\right|_1\tag{4}\label{eq:four}.
$$

This objective function measures the population sparsity on the $$i$$-th
training example.  As the activations are constrained to lie on the closed surface of the
unit $$\ell_2$$-ball, minimising this function requires that the activations lie as far as possible
from each other on this surface.
This leads to competition
between the activations and in turn the features stored in
$$\textbf{W}$$.  An
increase in the contribution of one feature to the representation for a given training example will
lead to a decrease in the contribution from all other features.
Similarly if the contribution from one feature is decreased all others
are increased. We show this effect in Figure. 1, where the
initial cost calculated from the circular points is minimised when
individual training examples can be represented by a single active feature
(blue and yellow squares i.e. when they lie on an axis) or a minimal
representation by two features (orange square).  In
Equation \ref{eq:two} the activations are constrained such
that they have the same expected square value known as *high dispersal*.  Optimising for
population sparsity and enforcing high dispersal is sufficient to meet the
lifetime sparsity requirement.  In other words, if activations are required to be equally active
on average across all examples and each example is forced to be
represented by only a few active (non-zero) features, then we can expect that
each feature will only be active for a few examples. 

![Figure 1.](/images/deriving-gradients-for-sparse-filtering-backpropagation/SF_visual.jpg){: .center-image}
*Figure 1. Optimising for population sparsity. The circles show the initial feature representation of three training examples. The size of the points shows the relative contribution of each example to the cost. After optimising for population sparsity, sparse filtering has learned features that can uniquely represent the pink and green examples. Due to enforcing high dispersal the third example must be represented by a minimal combination of both learned features, where the activation of each is equal. This incurs a higher cost compared to the others. This demonstrates how the learned features are sparsely distributed over the surface of the $$\ell_2$$-ball.*

To minimise Equation \ref{eq:four} we rely on the backpropagation idea (see above), where the normalisation steps are treated as
layers of a neural network with the weights of connections between
neurons given by the identity matrix.  Taking

$$
\begin{equation}
g(\textbf{z}_j) = ||\textbf{z}_j||^{}_2\tag{5}\label{eq:five}
\end{equation}
$$

where $$\textbf{z}_j \in \mathbb{R}^{K}$$ is the input to the $$j$$-th layer and $$K$$
is the number of features to learn. The gradients for backpropagation are given by

$$
\begin{equation}
g'(\textbf{z}_j) = \frac{||\textbf{z}_j||^{}_2\ \frac{d}{d\textbf{z}_j}\ \textbf{z}_j - \textbf{z}_j\sum^n_{i=1}\ \textbf{z}_j\ \frac{d}{d\textbf{z}_j}\ \textbf{z}_j}{||\textbf{z}_j||_2^2}\tag{6}\label{eq:six}.
\end{equation}
$$

Backpropagation through the normalisation layers then follows as

$$
\begin{align}
\boldsymbol{\delta}^{(4)} &= \frac{1}{||\tilde{\textbf{a}}||^{}_2} -
                    \frac{\hat{\textbf{a}}\sum^K_{i=1}\tilde{\textbf{a}}}{||\tilde{\textbf{a}}||^2_2}\tag{7}\label{eq:seven}
  \\
\boldsymbol{\delta}^{(3)} &= \textbf{I}^T \boldsymbol{\delta}^{(4)} \bullet\left( \frac{1}{||\textbf{a}||^{}_2} -
                    \frac{\tilde{\textbf{a}}\sum^m_{i=1}\textbf{a}}{||\textbf{a}||^2_2}\right)\tag{8}\label{eq:eight}.
\end{align}
$$

where $$\bullet$$ denotes the
Hadamard or elementwise product operator.  The errors must also be passed back through the activation
function (Equation \ref{eq:one}) to obtain the gradient with respect to $$\textbf{W}$$.

$$
\begin{equation}
\boldsymbol{\delta}^{(2)} = \textbf{W}^T \boldsymbol{\delta}^{(3)} \bullet \frac{\textbf{W}\textbf{X}}{\textbf{a}}\tag{9}\label{eq:nine}
\end{equation}
$$

This gives

$$
\begin{equation}
\nabla_{\textbf{W}}J\left(\textbf{W}\right) = \boldsymbol{\delta}^{(2)}\textbf{X}^T\tag{10}\label{eq:ten}
\end{equation}
$$

which may be used in gradient descent.

Working through the above helped me interpret the implementation provided with the original paper.  If you would
like to play with sparse filtering in python my implementation is available on [github][github].

[ngiam11]: https://papers.nips.cc/paper/4334-sparse-filtering.pdf
[ps1]: http://www.ifa.hawaii.edu/research/Pan-STARRS.shtml
[psst]: https://star.pst.qub.ac.uk/ps1threepi/psdb/
[rbfactor]: https://star.pst.qub.ac.uk/ps1threepi/psdb/public/
[code]: https://github.com/jngiam/sparseFiltering
[backprop]: http://ufldl.stanford.edu/wiki/index.php/Deriving_gradients_using_the_backpropagation_idea 
[coates2011]: http://proceedings.mlr.press/v15/coates11a/coates11a.pdf
[willmore2001]: http://www.cnbc.cmu.edu/~samondjm/papers/WillmoreandTolhurst2001.pdf
[github]: https://github.com/dr-darryl-wright/sparse_filtering
