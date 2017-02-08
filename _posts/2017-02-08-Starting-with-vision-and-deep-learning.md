---
layout: post
title: "Exploring Recent Video Action Recognition Research"
description: "Video Action Recognition is a great field for research in Deep Learning and methods developed for Video Action Recognition have used Convolutional Neural Networks, Recurrent Neural Networks, LSTMs, etc. They use information from spatial stream (single frame) as well as temporal stream (across multiple frames) to provide good classification accuracies."
date: 2017-02-08
updated: 2017-02-08
---

<h2 class="post-title"> Large Scale Video Classification with Convolutional Neural Networks </h2>
<ul class="content-subtitle">
    <li> Conference on Computer Vision and Pattern Recognition </li>
    <li><em> 2014 </em></li>
</ul>
<hr class="style-one section-rule" />
<p class="post"> 1. Provide an extensive <em>empirical</em> evaluation of CNNs on large scale video classification task using a new dataset of 1M YouTube videos belonging to 487 classes. </p>
<p class="post"> 2. <strong> What temporal connectivity pattern in a CNN architecture is best at taking advantage of local motion information present in the video? </strong> <br />
    For temporal information fusion in the CNNs, they explore 3 different approaches. <em> They have used a single-frame AlexNet-like baseline architecture. Using shorthand, the full architecture is C(96,11,3)-N-P-C(256,5,1)-N-P-C(384,3,1)-N-P-C(384-3-1)-C(256,3,1)-P-FC(4096)-FC(4096). C(d,f,s) means d filters of size fxf, applied with stride s. FC(n) is fully-connected layer with n nodes </em>. <br />
    <strong>Early Fusion </strong>: Apply filter on first convolutional layer in baseline model of size 11 x 11 x 3 x <em>T</em> where <em>T</em> is the temporal extent (say <em>T</em> = 10) and gather information across the entire extent. <br />
    <strong>Late Fusion </strong>: Two baseline networks with shared parameters 15 frames apart, fused at the first fully-connected layer. Neither baseline networks can detect any motion, but the FC-layer can computer global motion characteristics using output of two networks (aka towers, as in the paper). <br />
    <strong>Slow Fusion </strong>: Balanced mix between the two approaches above. Higher layers get progressively more global information in both spatial and temporal dimensions. First convolutional layer has filter with <em>T</em> = 4 and stride 2; second and third with <em>T</em> = 2 and stride 2. <br />
    <strong> As it turns out in the end, <em> Slow Fusion </em> is the answer </strong>.
</p>