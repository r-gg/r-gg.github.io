---
layout: page
title: Natural Language Processing
description: Feature Extraction and Deep Learning with BERT & LSTMs
img: assets/img/nlp_ml/lstm.jpg
# redirect: https://unsplash.com
importance: 3
category: data science
---

<span class="lead"><span class="badge badge-pill badge-primary">natural language processing</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">BERT</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">LSTM</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">transfer learning</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">recurrent neural networks</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">AG News</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Amazon Reviews</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">tensorflow</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">keras</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">transformers</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">optuna</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">keras-tuner</span></span>


<span class="lead"><span class="badge badge-pill badge-secondary">Development Period: 12.2022 - 02.2023</span></span>


## Co-Authors

Project implemented together with my colleagues:
- Branimir Raguž
- Stefan Miljević
  
as a part of the Machine Learning course.

## Description

During this project we evaluated and compared the performance of shallow models with traditional feature extraction (uni- and bi-gram vectorization) vs (transfer learning) [BERT](https://en.wikipedia.org/wiki/BERT_(language_model)) vs [LSTMs](https://en.wikipedia.org/wiki/Long_short-term_memory) on the [AG News](https://huggingface.co/datasets/ag_news) and [Amazon Reviews](https://www.kaggle.com/datasets/kritanjalijain/amazon-reviews) datasets.


### Baseline

As shallow model baselines **single-hidden-layer neural networks** and **support vector machines**. We extracted the features with *uni- and bi-gram vectorization*. Shallow models were tuned with [`optuna`](https://optuna.org/) framework.

### Deep Learning

To obtain more samples necessary for deep learning models, **data augmentation** (synonym replacement) has firstly been performed. **BERT** model was downloaded from [Hugging Face](https://huggingface.co/) and trained with [`transformers`](https://huggingface.co/docs/transformers/en/index) library. **LSTM** was developed with `keras` and tuned with `keras-tuner`. Custom embeddings were created as input for the LSTM due to the small size of the dataset. 

> The results of this project are available in the [report document](https://r-gg.github.io/assets/pdf/Ml Exercise 3.pdf).


> Code available in the [Github repository](https://github.com/r-gg/ml-37/tree/main/Exercise%203)