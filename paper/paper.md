---
title: 'Time Series Classification in R'
tags:
  - R
  - Time Series Classification
  - Functional Data
authors:
  - name: Florian Pfisterer
    orcid: 0000-0001-8867-762X
    affiliation: 1
  - name: Yu Wang
    orcid: 0000-0002-8319-2997
    affiliation: 2
  - name: Xudong Sun
    orcid: 0000-0001-9234-4932
    affiliation: 1
  - name: Bernd Bischl
    orcid: 0000-0001-6002-6980
    affiliation: 1
affiliations:
 - name: LMU Munich
   index: 1
 - name: TU Munich
   index: 2
date: 31.10.2019
bibliography: paper.bib
output: pdf_document

---

# Summary
Time series classification problems arise in many different domains such as speech recognition, medical signals, gesture recognition [@geurts2001pattern], or in industry often as a byproduct of measuring production processes.
A prominent example for time-series data are ECG data, where the heart's electrical activity is measured over time.

Due to the widespread application domains, algorithms for time-series classification have been widely studied.
Yet many modern methods are not available in R [@team2013r].

In order to compare different algorithms, 20 different TSC algorithms were implemented in a common Java framework integrated with the WEKA toolkit [@hallweka] by [@Bagnall2017].
This made a benchmark comparison between different algorithms feasible.
[@Bagnall2017] implement many current state-of-the-art algorithms, such as *HIVE*, *HIVE-COTE*, *BOSS* and others.
They find that several methods, such as *HIVE-COTE* [@hivecote] outperform many other methods including convolutional neural networks.
Because of a focus on a reproducible benchmark, no real user-interface for training and testing on datasets is made available.
We aim to make these algorithms available to a wider audience. Currently, state-of-the-art algorithms are only available in Java.
The R ecosystem on the other hand already offers several implementations for pre-processing, smoothing and imputation of time-series data, and users might often need the best of both worlds.
To achieve this, we adapt the codebase from [@Bagnall2017] in order to enable training and prediction on user-supplied data and hyperparameters.


With this software, we aim to make state-of-the-art algorithms for time-series classification available to scientists and users. A benchmark of the various algorithms can be obtained from the [Time Series Classification Repository](http://timeseriesclassification.com/).
Users can train over 30 time-series classification methods with specified hyper-parameters and use the learned models to predict future data.
Training models is made possible from *data.frames* as well as *arff* files.
The software currently focuses on 1-dimensional time-series measured on evenly spaced grids.
We aim to extend the software, once implementations of multi-dimensional algorithms are available.

We interface the Java methods using **rJava** [@urbanek2013rjava] in order to provide an easily accessible interface to the R computing language.
Additionally, we provide documentation for the integrated methods which is not easily available from [@Bagnall2017].
Our software enables seamless access to the Time Series Classification algorithms implemented in Java from R, and allows users to combine many different methods implemented in R e.g. for time-series preprocessing with several state-of-the-art time-series classifiers.

The software is available at [TSClassification](https://github.com/compstat-lmu/TSClassification), with its Java source code at [jTSC4R repository](https://github.com/compstat-lmu/jTSC4R).

---
nocite: tsclassif
---

# References



