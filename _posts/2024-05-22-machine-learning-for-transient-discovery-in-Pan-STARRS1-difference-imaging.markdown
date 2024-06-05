---
layout: post
title:  "Machine learning for transient discovery in Pan-STARRS1 difference imaging"
date:   2024-05-22 11:31:47 -0500
categories: project
---

**In this work we built a machine learning solution to reduce the number of artefacts that required manual from tens of thousands each day to a few hundred. The trade-off was that a few (<10) real detections were mistakenly discarded.**

[paper link](https://academic.oup.com/mnras/article/449/1/451/1315144)

### Motivation
* The study of astronomical transients is hindered by the need for humans to manually select promising candidates among many artefacts.

* These artefacts arise in the images of ground-based time-domain surveys with large CCD cameras.

*  This dependence on humans to reject bogus detections is unsustainable for next generation all-sky surveys.

![](/images/machine-learning-for-transient-discovery-in-Pan-STARRS1-difference-imaging/m_stv292fig1.jpeg)

### Methods
* In this study, we explored a simple machine learning approach to real–bogus classification by constructing a training set from the image data of ∼32 000 real astrophysical transients and bogus detections from the [Pan-STARRS1](https://en.wikipedia.org/wiki/Pan-STARRS) [Medium Deep Survey](https://outerspace.stsci.edu/display/PANSTARRS/PS1+Description+of+the+surveys#PS1Descriptionofthesurveys-MediumDeepSurvey:~:text=comm.%20%2D%20needs%20checking%5D-,Medium%20Deep%20Survey,-The%2010%20fields).

* The feature representation was derived from the pixel intensity values of a 20 × 20 pixel stamp around the centre of candidates. This differs from previous work in that it works directly on the pixels rather than hand-engineered features relying on domain knowledge.

* Three machine learning algorithms are trained (artificial neural networks, support vector machines and random forests) and their performances are tested on a held-out subset of 25 percent of the training data.

### Results
* We found the best results from the random forest classifier and demonstrate that by accepting a false positive rate of 1 percent, the classifier initially suggests a missed detection rate of around 10 percent.

* Retrospective analysis of misclassified cases found that a combination of bright star variability, nuclear transients and uncertainty in human labelling means that the missed detection rate is likely closer to 6 percent.

![](/images/machine-learning-for-transient-discovery-in-Pan-STARRS1-difference-imaging/m_stv292fig8.jpeg)

![](/images/machine-learning-for-transient-discovery-in-Pan-STARRS1-difference-imaging/m_stv292fig7.jpeg)

![](/images/machine-learning-for-transient-discovery-in-Pan-STARRS1-difference-imaging/m_stv292fig16.jpeg)