---
layout: page
title: Serverless Performance Isolation 
description: Survey on performance isolation methods in serverless edge-cloud
img: assets/img/perf_isol/multi-tenant.jpg
# redirect: https://unsplash.com
importance: 1
category: distributed & cloud
---
**Development Period:** *07.2023 - 11.2023*

**Keywords:** *performance isolation, performance interference, serverless computing, virtualization, function as a service, resource management*

**Mentor: Assistant Prof. Dipl.-Ing. Dr.techn. Stefan Nastić** 

## Abstract

The serverless computing paradigm has established itself as a flexible model for deploying applications in the cloud and at the edge. The serverless paradigm delegates many responsibilities from the developers to the serverless platform providers including enforcing performance isolation among the serverless functions. 
This work aims to provide insights into state-of-the-art methods that deal with the challenges of performance isolation in the edge-cloud context. The selected approaches are assessed by multiple criteria such as the technique used to achieve isolation, on which virtualization level is the isolation enforced, the decision-making approach, and the main isolation technique. 

Our analysis identifies three main groups of performance isolation approaches:
1. Resource reallocation / Capping approaches (43% of the analyzed approaches), 
2. Scheduling approaches (30%), and 
3. other approaches (27%). 

We discuss the representative approaches from each of these groups, analyze the limitations of the state-of-the-art, and outline potential future research directions in this promising research area. 
Our main findings are that: 
1. there is still insufficient support for performance isolation at the Edge,  
2. better support for managing (and tuning) cost-efficiency vs. performance-isolation trade-offs is needed,
3. novel metrics are needed to monitor and quantify performance interference across the Edge-Cloud, 
4. heterogeneity and unpredictability of serverless workloads are the main challenges to performance isolation,  
5. serverless databases suffer due to limited performance isolation, 
6. tighter integration of security aspects with performance isolation techniques is needed to avoid leaking exploitable information, and 
7. hybrid approaches are needed to provide a unified view on multiple aspects of performance isolation in the Edge-Cloud.
