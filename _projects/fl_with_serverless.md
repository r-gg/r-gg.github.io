---
layout: page
title: Federated Learning with Serverless
description: Implementation of federated learning on a Kubernetes cluster with Apache Openwhisk
img: assets/img/fl_serverless/fl _serverless1.png
importance: 1
category: distributed & cloud
related_publications: false
---

**Keywords**: *Serverless, Federated Learning, Kubernetes, Apache Openwhisk, MinIO, Kafka, kind*

## Co-Authors

Project completed together with:
- Matthias Schellner
- Dominik Nussbaumer
- Steven Ludwig

as a part of Serverless Computing course at TU Wien.

## Description

This project focuses on training a neural network model to recognize digits using serverless computing. It leverages serverless functions to handle the computational tasks, ensuring scalability and efficiency. The architecture employs Openwhisk, operating on a Kubernetes environment, with the functions written in Python. The project utilizes a local Kubernetes cluster simulation using 'kind' (Kubernetes in Docker). 

Implementation of the serverless approach is compared to classical federated learning setting across multiple KPIs (accuracy, train time, memory usage, cpu usage, cost, cost efficiency)/

> Code available in the <a href="https://github.com/r-gg/serverless-computing">Github repository</a>.

## Architecture

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/fl_serverless/ow-impl.png" title="Implementation Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Architecture of the solution.
</div>