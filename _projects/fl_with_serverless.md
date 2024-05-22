---
layout: page
title: Serverless FL
description: Implementation of federated learning on a Kubernetes cluster with Apache Openwhisk
img: assets/img/fl_serverless/fl _serverless1.png
importance: 1
category: distributed & cloud
related_publications: false
---
<span class="lead"><span class="badge badge-pill badge-primary">Federated Learning</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Serverless</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Kubernetes</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Docker</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Privacy-preserving ML</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Scripting & Automation</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Apache Openwhisk</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">MinIO</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Kafka</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">kind</span></span>



<span class="lead"><span class="badge badge-pill badge-secondary">Development Period: 11.2023 - 01.2024</span></span>


## Co-Authors

- Matthias Schellner
- Dominik Nussbaumer
- Steven Ludwig


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