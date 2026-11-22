# Literature for my bachelor's thesis: steganalysis of digital images

This repository collects the literature I am using for my bachelor's thesis on detecting steganography in images. 

Contents:

* README.md: this file, with a note for each source on what I use it for.
* references.bib: complete bibliographic information for every source.
* sources\_database.xlsx: the same list as a spreadsheet (authors, title, year, short summary).
* pdfs: the papers whose licence allows sharing them (open access). For every other source there is a link to the publisher's page (DOI) and, where one exists, a link to a free copy posted by the authors or in an open archive.

Each source below has the same parts: what it is about, and what I use it for.

## Background

### J. Fridrich, Steganography in Digital Media: Principles, Algorithms, and Applications (2009)

* PDF: not included (commercial book from Cambridge University Press).
* Publisher page: https://doi.org/10.1017/CBO9781139192903
* About: textbook. Chapters 2 to 4 cover how digital images are captured and represented. Chapters 10 onwards cover the basics of steganalysis.
* What I use it for: the theory background of my thesis: image formats and noise, and the general framework of steganalysis that my detectors fit into.

### V. Holub, J. Fridrich, T. Denemark, Universal Distortion Function for Steganography in an Arbitrary Domain (2014)

* PDF: included
* Publisher page: https://doi.org/10.1186/1687-417X-2014-1
* About: UNIWARD, an embedding method that minimizes a distortion function so the message goes where it is hardest to detect.
* What I use it for: an example of modern content-adaptive steganography, which shows how far the LSB methods I test are from current embedding methods.

## Classic detectors of LSB steganography

### A. Westfeld, A. Pfitzmann, Attacks on Steganographic Systems (1999 workshop, published 2000)

* PDF: not included.
* Publisher page: https://doi.org/10.1007/10719724\_5
* About: the chi-squared attack on LSB embedding, and visual attacks.
* What I use it for: I implemented the chi-squared attack as my first detector and tested it on sequential and random LSB replacement and LSB matching.

### J. Fridrich, M. Goljan, R. Du, Reliable Detection of LSB Steganography in Color and Grayscale Images (2001)

* PDF: not included.
* Publisher page: https://doi.org/10.1145/1232454.1232466
* Free copy: https://ws2.binghamton.edu/fridrich/Research/acmwrkshp\_version.pdf (author's page)
* About: RS analysis, which estimates the length of a message hidden with LSB replacement from how flipping LSBs changes groups of pixels.
* What I use it for: I implemented RS analysis as my second detector and compared it with the chi-squared attack on the same images.

### S. Dumitrescu, X. Wu, Z. Wang, Detection of LSB Steganography via Sample Pair Analysis (2003)

* PDF: not included
* Publisher page: https://doi.org/10.1109/TSP.2003.812753
* Free copy: https://www.ece.mcmaster.ca/\~sorina/papers/LSBfinalTSP.pdf (author's page)
* About: sample pair analysis, another method that estimates the hidden message length for LSB replacement, using a finite state machine over pairs of pixels.
* What I use it for: related work next to RS analysis; a possible third classic detector.

## Feature-based (machine learning) steganalysis

### T. Pevný, P. Bas, J. Fridrich, Steganalysis by Subtractive Pixel Adjacency Matrix (2010)

* PDF: not included.
* Publisher page: https://doi.org/10.1109/TIFS.2010.2045842
* Free copy: https://hal.science/hal-00541410/document (HAL open archive)
* About: SPAM features, which model differences between neighbouring pixels as a Markov chain and feed them to a classifier.
* What I use it for: the next step of my practical work: a SPAM-based detector for LSB matching, which the chi-squared attack and RS analysis detect poorly.

### J. Fridrich, J. Kodovský, Rich Models for Steganalysis of Digital Images (2012)

* PDF: not included.
* Publisher page: https://doi.org/10.1109/TIFS.2012.2190402
* Free copy: https://ws2.binghamton.edu/fridrich/Research/TIFS2012-SRM.pdf (author's page)
* About: rich models, very large feature sets built from many noise residuals, with an ensemble classifier.
* What I use it for: related work; the main feature-based approach after SPAM and before deep learning.

### J. Kodovský, J. Fridrich, V. Holub, Ensemble Classifiers for Steganalysis of Digital Media (2012)

* PDF: not included.
* Publisher page: https://doi.org/10.1109/TIFS.2011.2175919
* Free copy: https://ws2.binghamton.edu/fridrich/Research/ensemble-doubleColumn.pdf (author's page)
* About: ensemble classifiers (random forests) as a faster alternative to SVMs for high-dimensional steganalysis features.
* What I use it for: a possible classifier for the SPAM step, and related work.

## Deep learning steganalysis

### M. Chaumont, Deep Learning in Steganography and Steganalysis from 2015 to 2018 (2020)

* PDF: not included.
* Publisher page: https://doi.org/10.1016/B978-0-12-819438-6.00022-0
* Free copy: https://arxiv.org/abs/1904.01444 (arXiv preprint)
* About: book chapter reviewing the convolutional neural networks used for steganalysis from 2015 to 2018.
* What I use it for: overview for the deep learning part of my related work.

### G. Xu, H.-Z. Wu, Y.-Q. Shi, Structural Design of Convolutional Neural Networks for Steganalysis (2016)

* PDF: not included.
* Publisher page: https://doi.org/10.1109/LSP.2016.2548421
* What I use it for: suggested by my advisor as one of the first CNNs for steganalysis; cited through the reviews above.

### J. Ye, J. Ni, Y. Yi, Deep Learning Hierarchical Representations for Image Steganalysis (2017)

* PDF: not included.
* Publisher page: https://doi.org/10.1109/TIFS.2017.2710946
* What I use it for: suggested by my advisor as an early CNN for steganalysis; cited through the reviews above.

### M. Boroumand, M. Chen, J. Fridrich, Deep Residual Network for Steganalysis of Digital Images (2019)

* PDF: not included.
* Publisher page: https://doi.org/10.1109/TIFS.2018.2871749
* Free copy: https://ws2.binghamton.edu/fridrich/Research/SRNet.pdf (author's page)
* About: SRNet, a deep residual network that works for both spatial and JPEG images with few hand-designed parts.
* What I use it for: related work; a state-of-the-art detector to compare the classic methods against.

### H. Kheddar, M. Hemis, Y. Himeur, D. Megías, A. Amira, Deep Learning for Steganalysis of Diverse Data Types (2024)

* PDF: included
* arXiv page: https://arxiv.org/abs/2308.04522
* Published version: https://doi.org/10.1016/j.neucom.2024.127528
* About: recent review of deep learning steganalysis for images, audio and video, with datasets and evaluation metrics.
* What I use it for: a recent overview of the field, for related work.

## Datasets, competitions and practical issues

### P. Bas, T. Filler, T. Pevný, "Break Our Steganographic System": The Ins and Outs of Organizing BOSS (2011)

* PDF: not included.
* Publisher page: https://doi.org/10.1007/978-3-642-24178-9\_5
* Free copy: https://hal.science/hal-00648057/document (HAL open archive)
* About: the BOSS steganalysis challenge, the HUGO algorithm made for it, and its image databases, including BOSSBase.
* What I use it for: BOSSbase is the image set I use in my experiments, so this is the reference for it.

### A. D. Ker et al., Moving Steganography and Steganalysis from the Laboratory into the Real World (2013)

* PDF: not included.
* Publisher page: https://doi.org/10.1145/2482513.2482965
* Free copy: https://hal.science/hal-00836407/document (HAL open archive)
* About: position paper on the open problems of using steganography and steganalysis outside laboratory conditions.
* What I use it for: discussing the limitations of my results, which come from laboratory conditions.

### R. Cogranne, Q. Giboulot, P. Bas, ALASKA#2: Challenging Academic Research on Steganalysis with Realistic Images (2020)

* PDF: not included.
* Publisher page: https://doi.org/10.1109/WIFS49906.2020.9360896
* Free copy: https://utt.hal.science/hal-02950094/document (HAL open archive)
* About: the ALASKA#2 challenge on Kaggle, where deep learning detectors beat earlier methods on more realistic images.
* What I use it for: shows that results on BOSSbase alone may not carry over to realistic images; part of the limitations discussion.

