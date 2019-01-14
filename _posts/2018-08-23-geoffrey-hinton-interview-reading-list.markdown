---
layout: post
title:  "Geoffrey Hinton Interview Reading List"
date:   2018-08-22 11:31:47 -0500
categories: reading list
---
Below is an incomplete reading list of some of the papers mentioned in the deeplearning.ai interview with Geoffrey Hinton. I’m still missing references for Yoshua Bengio’s work on embeddings for words in English text and Yee Whye Teh’s work on training multiple RBM layers as a single model. I’ll add these if I can find them.

*Update: Mnay thanks to Aleksandar Trifunovic on the coursera forums for providing links to the missing references. I'm still uncertain which work Geoffrey Hinton was referring to in relation to Yoshua Bengio’s work on embeddings for words in English text from the 90s.  Aleksandar's reference is from 2015 and I have found another from 2003, I have included both these below.*

Karl Lashley’s experiments - [In Search Of The Engram. Lashley (1950)][Lashley1950]

A modern review of the above - [In search of the engram, 2017. Berlot, Popp and Diedrichsen (2017)][Berlot2017]

Backprop in Nature - [Learning representations by back-propagating errors. Rumelhart, Hinton and Williams (1986)][Rumelhart1986]

Work with Terry Sejnowski on Boltzmann machines:

 - [Massively parallel architectures for A.I.: Netl, Thistle, and Boltzmann machines. Fahlman, Hinton and Sejnowski (1983)][Fahlman1983]

 - [Boltzmann Machines: Constraint satisfaction networks that learn. Hinton, Sejnowski and Ackley (1984)][Hinton1984]

 - [A learning algorithm for Boltzmann machines. Ackley, Hinton and Sejnowski (1985)][Ackley1985]

 - [Learning and relearning in Boltzmann machines. Hinton and Sejnowski (1986)][Hinton1986]

 - [Separating figure from ground using a Boltzmann machine. Sejnowski and Hinton (1987)][Sejnowski1987]

Yoshua Bengio’s work on embeddings for words in English text:
 - [Learning to understand phrases by embedding the dictionary. Hill et al. (2015)][Hill2015]
 - [A Neural Probabilistic Language Model. Bengio et al. (2003)][Bengio2003]
 
Restricted Boltzmann Machines and Netflix - [Restricted Boltzmann Machines for Collaborative Filtering. Salakhutdinov, Mnih and Hinton (2007)][Salakhutdinov2007]

Another Restricted Boltzmann Machine application - [Phone Recognition using Restricted Boltzmann Machines. Mohamed and Hinton (2010)][Mohamed2010]

Training Deep RBMs as a single Model - [Learning to Understand Phrases by Embedding the Dictionary. Hinton, Osindero and Teh (2006)][Hinton2006]

Approximate Inference in Deep Belief Nets - [Variational Learning in Nonlinear Gaussian Belief Networks. Frey and Hinton (1998)][Frey1998]

Approximate E-step in EM - [Keeping Neural Networks Simple by Minimizing the Description Length of the Weights. Hinton and van Camp (1993)][Hinton1993]

Dropout - [Dropout: A Simple Way to Prevent Neural Networks from Overfitting. Srivastava et al. (2014)][Srivastava2014]

ReLU - [Rectified Linear Units Improve Restricted Boltzmann Machines. Nair and Hinton (2010)][Nair2010]

Recirculation Algorithm - [Learning representations by recirculation. Hinton and McClelland (1988)][Hinton1988]

Spike-Timing-Dependent Synaptic Plasticity - [Competitive Hebbian learning through spike-timing-dependent synaptic plasticity. Song, Miller and Abbott (2000)][Song2000]

Fast weights - [Using Fast Weights to Attend to the Recent Past. Ba et al. (2016)][Ba2016]

Capsule Networks - [Dynamic Routing between Capsules. Sabour, Frosst and Hinton (2017)][Sabour2017]

[Lashley1950]: http://gureckislab.org/courses/fall13/learnmem/papers/Lashley1950.pdf 
[Berlot2017]: http://www.diedrichsenlab.org/pubs/Berlot_CurrentOpinion_2017.pdf
[Rumelhart1986]: https://www.nature.com/articles/323533a0.pdf
[Fahlman1983]: http://www.cs.toronto.edu/~hinton/absps/fahlmanBM.pdf
[Hinton1984]: http://www.cs.toronto.edu/~hinton/absps/bmtr.pdf
[Ackley1985]: http://www.cs.toronto.edu/~hinton/absps/cogscibm.pdf
[Hinton1986]: http://www.cs.toronto.edu/~hinton/absps/pdp7.pdf
[Sejnowski1987]: http://www.cs.toronto.edu/~hinton/absps/arbibfigground.pdf
[Hill2015]: https://arxiv.org/pdf/1504.00548.pdf
[Bengio2003]: http://www.jmlr.org/papers/volume3/bengio03a/bengio03a.pdf
[Salakhutdinov2007]: http://www.cs.toronto.edu/~fritz/absps/netflix.pdf
[Mohamed2010]: http://www.cs.toronto.edu/~hinton/absps/icassp10.pdf
[Hinton2006]: http://www.cs.toronto.edu/~fritz/absps/ncfast.pdf
[Frey1998]: http://www.cs.toronto.edu/~fritz/absps/nlgbn.pdf
[Hinton1993]: http://www.cs.toronto.edu/~hinton/absps/colt93.pdf
[Srivastava2014]: http://www.cs.toronto.edu/~hinton/absps/JMLRdropout.pdf
[Nair2010]: http://www.cs.toronto.edu/~hinton/absps/reluICML.pdf
[Hinton1988]: http://www.cs.toronto.edu/~hinton/absps/recirculation.pdf
[Song2000]: http://www.columbia.edu/cu/neurotheory/Larry/SongNatNeuro00.pdf
[Ba2016]: https://arxiv.org/pdf/1610.06258.pdf
[Sabour2017]: https://arxiv.org/pdf/1710.09829.pdf
