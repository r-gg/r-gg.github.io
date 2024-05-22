---
layout: page
title: COVID Stay Days 
description: EDA & Modeling with NNs and RFs
img: assets/img/bachelor/bachelor.png
importance: 1
category: data science
related_publications: false
---

<span class="lead"><span class="badge badge-pill badge-primary">Python</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">ordinal regression</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">ordinal classification</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">machine learning</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">random forests</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">neural networks</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">pandas</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">numpy</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">matplotlib</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">COVID-19</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Hospitalization length prediction</span></span>

<span class="lead"><span class="badge badge-pill badge-secondary">Development Period: 03.2022 - 06.2022</span></span>




## Abstract 

Due to the COVID-19 pandemic, hospitals on the global scale faced major issues and multiple severe capacity shortages, especially in the first year of the pandemic. One of the ways to disburden the hospital management staff and improve the quality of bed assignments in the intensive care unit (ICU) can be seen in the employment of machine learning (ML) models. These models can provide the ICU administrative staff with the information needed to improve the quality of bed allocations. Various disease and patient-related metrics can be predicted with ML models, including the length of hospital stay (LoS) of each patient. Predicting this metric is the first central point of this thesis. Along with that, the thesis aims to provide an empirical comparison of the two different ML model types that are tailored for solving ordinal regression problems. The first is a representative of the Random Forest (RF) models and the second of the Neural Network (NN) paradigm. 

In order to achieve the stated goals, the central topics of the thesis will be introduced along with screening, analysis, and the presentation of state-of-the-art literature on these subjects. Based on the screened literature, eight models are then developed (four RF and four NN models). Half of them implement the naive methodology and the other half the optimized approaches to ordinal regression. Another differentiation criterion is whether four or two classes are being predicted. The eight models are then evaluated and compared, not only to one another but also to the models developed in state-of-the-art literature and their value for the medical staff is assessed.

It has been established that the naive binary classification RF model achieved the best performance across multiple evaluation metrics (with respect to the given dataset). The model is capable of correctly identifying 89% of the patients who stay in the hospital for longer than 50 days, which could be beneficial for the ICU administration personnel. The results further show that models which are specifically tailored for ordinal regression achieve comparable and, in some cases, a worse performance than their naive counterparts on the provided dataset. It can, further, be observed that the RF models generally produce better results than the NN models if there are four classes in the response. Regarding the binary response, both RF and NN models achieve comparable performance across all considered metrics.

> Code available in the [GitHub repository](https://github.com/r-gg/covid-19-eda-nn-rf)

## Plots

### EDA

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bachelor/ba_3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bachelor/ba_4.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bachelor/ba_5.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Distribution of the stay days variable before (left) and after merging into four (middle) and two classes (right).
</div>

### Neural networks vs Random forests

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bachelor/bachelor.png" title="RF vs NN" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison of different performance metrics for both Neural Networks and Random Forests (naive and optimized models) where the response contains <strong>four</strong> classes
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bachelor/bachelor_2.png" title="RF vs NN" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison of different performance metrics for both Neural Networks and Random Forests (naive and optimized models) where the response contains <strong>two</strong> classes
</div>

