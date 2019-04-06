---
layout: post
title:  "Yoshua Bengio Interview Reading List"
date:   2019-03-21 11:31:47 -0500
categories: reading list
---

Similar to the [reading list from Geoffrey Hinton's interview][HintonInterview], below is another reading list where I have tried to gather together a list of references to work mentioned in [Andrew Ng's deeplearning.ai interview with Yoshua Bengio][Interview].  This was more difficult as specific papers weren't mentioned as often, but I have tried to pull together works that cover the topics discussed.  If you feel I have missed an important paper or if you feel the examples I've chosen don't best cover the intended topic let me know (I haven't read all these yet).  I have also included links to the proceedings of all ICLR conferences.

Activation Functions and Rectified Linear Units:
 - [Understanding the difficulty of training deep feedforward neural networks. Glorot and Bengio (2010)][Glorot2010]
 - [Deep Sparse Rectifier Neural Networks. Glorot, Bordes and Bengio (2011)][Glorot2011a]

Tackling the Curse of Dimensionality with Neural Networks - [Modeling High-Dimensional Discrete Data with
Multi-Layer Neural Networks. Bengio and Bengio (2000)][Bengio2000]

Distributed Representations:
 - [New Distributed Probabilistic Language Models. Bengio (2002)][Bengio2002]
 - [Distributed Representation Prediction for Generalization to New Words. Larochelle and Bengio (2006)][Larochelle2006]
 - [Learning General Purpose Distributed Sentence Representations via Large Scale Multitask Learning. Subramanian et al. (2018)][Subramanian2018]

Long-Term Dependencies:
 - [Learning to deal with long-term dependencies. Pascanu and Bengio (1986)][Pascanu1986]
 - [The problem of learning long-term dependencies in recurrent networks. Bengio, Frasconi and Simard (1993)][Bengio1993]
 - [Learning long-term dependencies with gradient descent is difficult. Bengio, Simard and Frasconi (1994)][Bengio1994a]
 - [Hierarchical Recurrent Neural Networks for Long-Term Dependencies. El Hihi and Bengio (1996)][ElHihi1996]
 - [Evaluating Long-Term Dependency Benchmark Problems by Random Guessing. Schmidhuber, Hochreiter and Bengio (1997)][Schmidhuber1997]
 - [Gradient Flow in Recurrent Nets: the Difficulty of Learning Long-Term Dependencies. Hochreiter et al. (2001)][Hochreiter2001]
 - [Modeling Temporal Dependencies in High-Dimensional Sequences: Application to Polyphonic Music Generation and Transcription. Boulanger-Lewandowski, Bengio and Vincent (2012)][Boulanger-Lewandowski2012]
 - [Towards Non-saturating Recurrent Units for Modelling Long-term Dependencies. Chandar et al. (2019)][Chandar2019]

Work on deep learning with stacks of autoencoders and RBMs:
 - [Extracting and Composing Robust Features with Denoising Autoencoders. Vincent et al. (2008)][Vincent2008]
 - [Stacked Denoising Autoencoders: Learning Useful Representations in a Deep Network with a Local Denoising Criterion. Vincent et al. (2010)][Vincent2010]
 - [Greedy layer-wise training of deep networks. Bengio et al. (2007)][Bengio2007]

Unsupervised Learning:
 - [The Difficulty of Training Deep Architectures and the Effect of Unsupervised Pre-Training. Erhan et al. (2009)][Erhan2009]
 - [Why Does Unsupervised Pre-training Help Deep Learning? Erhan et al. (2010)][Erhan2010]
 - [Unsupervised and Transfer Learning Challenge: a Deep Learning Approach. Mesnil et al. (2012)][Mesnil2012]
 - [Scaling Up Spike-and-Slab Models for Unsupervised Feature Learning. Goodfellow, Courville and Bengio (2013)][Goodfellow2013]
 - [Unsupervised Learning of Semantics of Object Detections for Scene Categorization. Mesnil et al. (2014)][Mesnil2014]
 - [Generalizable Features From Unsupervised Learning. Mirza et al. (2017)][Mirza2017]

Generative Adversarial Nets - [Generative Adversarial Nets. Goodfellow et al. (2014)][Goodfellow2014]
 
Neural Machine Translation:
 - [On the Properties of Neural Machine Translation: Encoder-Decoder Approaches. Cho et al. (2014)][Cho2014]
 - [Overcoming the Curse of Sentence Length for Neural Machine Translation using Automatic Segmentation. Pouget-Abadie et al. (2014)][PougetAbadie2014]
 - [A Character-Level Decoder without Explicit Segmentation for Neural Machine Translation. Chung et al. (2016)][Chung2016]

Neural Machine Translation with Attention:
 - [Multi-Way, Multilingual Neural Machine Translation with a Shared Attention Mechanism. Firat, Cho and Bengio (2016)][Firat2016]
 - [Fine-Grained Attention Mechanism for Neural Machine Translation. Choi, Cho and Bengio (2018)][Choi2018]

Biologically Plausible Learning:
 - [Towards Biologically Plausible Deep Learning. Bengio et al. (2016)][Bengio2016a]
 - [Feedforward Initialization for Fast Inference of Deep Generative Networks is Biologically Plausible. Bengio et al. (2016)][Bengio2016b]
 - [STDP-Compatible Approximation of Backpropagation in an Energy-Based Model. Bengio et al. (2017)][Bengio2017]
 
Credit Assignment and Backprop - [Credit Assignment through Time: Alternatives to Backpropagation. Bengio and Frasconi (1994)][Bengio1994b]

Learning from Few Examples - [MetaGAN: An Adversarial Approach to Few-Shot Learning. Zhang et al. (2018)][Zhang2018]

Domain Adaption - [Domain Adaptation for Large-Scale Sentiment Classification: A Deep Learning Approach. Glorot, Bordes and Bengio (2011)][Glorot2011b]

Causal Mechanisms - [A Meta-Transfer Objective for Learning to Disentangle Causal Mechanisms. Bengio et al. (2019)][Bengio2019]

Deep Learning Book - [Deep Learning (Adaptive Computation and Machine Learning series). Goodfellow, Bengio and Courville][book]

International Conference on Learning Representations:
 - [ICLR 2019][iclr2019]
 - [ICLR 2018][iclr2018]
 - [ICLR 2017][iclr2017]
 - [ICLR 2016][iclr2016]
 - [ICLR 2015][iclr2015]
 - [ICLR 2014][iclr2014]
 - [ICLR 2013][iclr2013]
 
[Glorot2010]: http://proceedings.mlr.press/v9/glorot10a/glorot10a.pdf?hc_location=ufi
[Glorot2011a]: http://proceedings.mlr.press/v15/glorot11a/glorot11a.pdf
[Bengio2000]: http://papers.nips.cc/paper/1679-modeling-high-dimensional-discrete-data-with-multi-layer-neural-networks.pdf
[Bengio2002]: https://www.researchgate.net/profile/Y_Bengio/publication/244436420_New_distributed_probabilistic_language_models/links/546b702c0cf2f5eb18091df1.pdf
[Larochelle2006]: http://www.iro.umontreal.ca/~lisa/bib/pub_subject/finance/pointeurs/dist_rep_pred_tr1284.pdf
[Subramanian2018]: https://arxiv.org/pdf/1804.00079.pdf
[Chandar2019]: https://arxiv.org/pdf/1804.00079.pdf
[ElHihi2006]: http://papers.nips.cc/paper/1102-hierarchical-recurrent-neural-networks-for-long-term-dependencies.pdf
[Boulanger-Lewandowski2012]: https://arxiv.org/pdf/1206.6392.pdf
[Hochreiter2001]: https://www.bioinf.jku.at/publications/older/ch7.pdf
[Schmidhuber1997]: https://www.researchgate.net/profile/Y_Bengio/publication/2383723_Evaluating_Long-Term_Dependency_Benchmark_Problems_By_Random_Guessing/links/546cd2710cf2193b94c577c5.pdf
[Pascanu1986]: http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.387.3148&rep=rep1&type=pdf
[Bengio1993]: https://www.researchgate.net/publication/224663746_Problem_of_learning_long-term_dependencies_in_recurrent_networks
[Bengio1994a]: http://www.comp.hkbu.edu.hk/~markus/teaching/comp7650/tnn-94-gradient.pdf
[Vincent2008]: http://delivery.acm.org/10.1145/1400000/1390294/p1096-vincent.pdf?ip=131.212.250.143&id=1390294&acc=ACTIVE%20SERVICE&key=70F2FDC0A279768C%2E3D342327617A783A%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35&__acm__=1554152016_33ea350e0e9d45467809645222506b1e
[Vincent2010]: http://www.jmlr.org/papers/volume11/vincent10a/vincent10a.pdf
[Bengio2007]: http://papers.nips.cc/paper/3048-greedy-layer-wise-training-of-deep-networks.pdf
[Erhan2009]: http://proceedings.mlr.press/v5/erhan09a/erhan09a.pdf
[Erhan2010]: http://www.jmlr.org/papers/volume11/erhan10a/erhan10a.pdf
[Mirza2017]: https://arxiv.org/pdf/1612.03809.pdf
[Mesnil2014]: https://link.springer.com/chapter/10.1007/978-3-319-12610-4_13
[Goodfellow2013]: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6389684
[Mesnil2012]: http://proceedings.mlr.press/v27/mesnil12a/mesnil12a.pdf
[Goodfellow2014]: http://papers.nips.cc/paper/5423-generative-adversarial-nets.pdf
[Cho2014]: https://arxiv.org/pdf/1409.1259.pdf
[Chung2016]: https://arxiv.org/pdf/1603.06147.pdf
[PougetAbadie2014]: https://arxiv.org/pdf/1409.1257.pdf
[Choi2018]: https://arxiv.org/pdf/1803.11407.pdf
[Firat2016]: https://arxiv.org/pdf/1601.01073.pdf
[Bengio2016a]: https://arxiv.org/pdf/1502.04156.pdf
[Bengio2016b]: https://arxiv.org/pdf/1606.01651.pdf 
[Bengio1994b]: http://papers.nips.cc/paper/724-credit-assignment-through-time-alternatives-to-backpropagation.pdf
[Bengio2017]: https://www.mitpressjournals.org/doi/full/10.1162/NECO_a_00934
[Zhang2018]: http://papers.nips.cc/paper/7504-metagan-an-adversarial-approach-to-few-shot-learning.pdf
[Glorot2011b]: http://www.iro.umontreal.ca/~lisa/bib/pub_subject/language/pointeurs/ICML2011_sentiment.pdf
[Bengio2019]: https://arxiv.org/pdf/1901.10912.pdf
[book]: https://www.amazon.com/Deep-Learning-Adaptive-Computation-Machine/dp/0262035618/ref=asc_df_0262035618/?tag=hyprod-20&linkCode=df0&hvadid=312128454859&hvpos=1o1&hvnetw=g&hvrand=9767831947003429721&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9019667&hvtargid=pla-416263148149&psc=1
[iclr2019]: https://openreview.net/group?id=ICLR.cc/2019/Conference 
[iclr2018]: https://openreview.net/group?id=ICLR.cc/2018/Conference
[iclr2017]: https://openreview.net/group?id=ICLR.cc/2017/conference
[iclr2016]: https://iclr.cc/archive/www/doku.php%3Fid=iclr2016:accepted-main.html
[iclr2015]: https://iclr.cc/archive/www/doku.php%3Fid=iclr2015:accepted-main.html
[iclr2014]: https://iclr.cc/archive/2014/conference-proceedings/
[iclr2013]: https://sites.google.com/site/representationlearning2013/conference-proceedings
[ElHihi1996]: https://papers.nips.cc/paper/1102-hierarchical-recurrent-neural-networks-for-long-term-dependencies.pdf
[Interview]: https://www.youtube.com/watch?v=pnTLZQhFpaE
[HintonInterview]: https://dr-darryl-wright.github.io/reading/list/2018/08/22/geoffrey-hinton-interview-reading-list.html 
