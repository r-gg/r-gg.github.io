---
layout: page
title: KNRM 
description: Implementation of Kernel-based Neural Re-Ranking Model
img: assets/img/adv_ir/knrm.png
# redirect: https://unsplash.com
importance: 2
category: data science
---
**Development Period:** *05.2023 - 06.2023*

**Keywords:** *information retrieval, neural IR, neural re-ranking, embedding, kernel pooling, pytorch*

Over the course Advanced Information Retrieval I implemented the **Kernel-based neural re-ranking model (KNRM)** as presented by [Xiong et al.](https://dl.acm.org/doi/abs/10.1145/3077136.3080809)

> Due to privacy regulations, the repository could not have been made public. Code upon request.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/adv_ir/knrm.png" title="KNRM Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The Architecture of K-NRM. Given input query words and document words, the embedding layer maps them into distributed representations, the translation layer calculates the word-word similarities and forms the trans- lation matrix, the kernel pooling layer generate soft-TF counts as ranking features, and the learning to rank layer combines the soft-TF to the final ranking score. Source:<a href="https://dl.acm.org/doi/abs/10.1145/3077136.3080809">Xiong et al.</a>
</div>

## Implementation

In the `init` method of the model, the Weights and Biases of the MLP part are initialized along with the word embeddings and the (gaussian) kernel statistics (mean and standard deviation).

The forward pass was adapted from the original implementation which is written with TensorFlow. Hence we adapted it to use Torch instead.

In the following the procedure is briefly described:
1. we firstly calculate the word embeddings for the query and the document as well as the query and document OOV masks.
2. query and document embeddings are then normalized and based on their normalized versions, the similarity matrix is computed
3. for each kernel, the similarity matrix is fed into the kernel function and the output is summed up over the document dimension
4. words which are OOV are masked out
5. the sum over the query dimension is build along with the query-term weighting
6. the summed up values are then fed into the MLP (tanh(m * W + b)) and the output is returned

There were not that many problems with translating the code from tensorflow to torch. However, in order to do it one had to really understand how the algorithm works.


### Hyperparameter tuning

We've spent a reasonable amount of time on hyperparameter tuning. We wanted to implement it with Ray tune at first, but we've encountered some problems (probably related to python version), hence we switched to optuna. With optuna we only tuned the value of the learning rate and this is extensible to the batch size and other model parameters as well. 

With hyperparam tuner we aim to maximize MRR@10. Other possibilities were maximizing the NDCG or MAP@k.
Hyperparameter tuning was performed with only a subset of the whole data:
- For training data, 1000 out of 2.4 mil
- For validation data we use all tuples

In total, 10 trials were executed in order to find the best learning rate. Each one had 2 epochs.

We of course set the seed to 1 for the optuna sampler to make the results reproducible.

The best learning rate found through these trials was:
```
 {'learning_rate': 0.00024112537061475754}
```

### Training and evaluation

In the validation and test .tsv files we are presented with a query and the top 40 relevant documents ranked by BM25. We have to re-rank these documents using our neural model and then evaluate the results using the msmarco qrels file, our fira aggregated judgements and the fira baseline judgements.

Due to slow training we have decided to reduce the training set size to 1/10 of the original set which is still plenty of samples (`240000`). Additionally we trained the model in two epochs.

Metrics used for evaluation with the MSMARCO test set were MRR@10 and NDCG@10.

#### Final results on the MSMARCO test set

- **MRR@10 0.1924**
- **NDCG@10 0.2459**
