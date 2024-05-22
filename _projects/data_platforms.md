---
layout: page
title: Data Platform Development
description: Developing an ETL process for a Bike Store Data Warehouse
img: assets/img/data_platform/dwh-architecture.png
# redirect: https://unsplash.com
importance: 2
category: data science
---

<span class="lead">
    <span class="badge badge-pill badge-primary">Data Warehousing</span>
    <span class="badge badge-pill badge-primary">Business Intelligence</span>
    <span class="badge badge-pill badge-primary">ETL</span>
    <span class="badge badge-pill badge-primary">ROLAP Cube</span>
    <span class="badge badge-pill badge-primary">Pentaho Data Integration</span>
    <span class="badge badge-pill badge-primary">SQL</span>
    <span class="badge badge-pill badge-primary">Multidimensional Expression (MDX) Queries</span>
    <span class="badge badge-pill badge-primary">Data Mart</span>
    <span class="badge badge-pill badge-primary">Sales Analysis</span>
    <span class="badge badge-pill badge-primary">MySQL</span>
    <span class="badge badge-pill badge-primary">Schema Workbench</span>
    <span class="badge badge-pill badge-primary">Star Schema</span>
    <span class="badge badge-pill badge-primary">Business Analytics</span>
    <span class="badge badge-pill badge-primary">Big Time Bikes</span>
</span>

<span class="lead"><span class="badge badge-pill badge-secondary">Development Period: 11.2022 - 12.2022</span></span>

## Overview

**In this project, our team developed a data platform focusing on the "Internet Sales" business area for a fictional company, Big Time Bikes. This platform integrates a data mart and a ROLAP cube to analyze sales data, assisting the management team in decision-making processes.**

## Project Structure

The project is structured into three main parts:

- **Part 1: Landing/Staging Area Setup**
  - We set up a landing/staging area to accommodate data from the OLTP system.
  - We implemented scripts to create tables and load data into the BI_Bikes database (`SQL`).

- **Part 2: Data Mart and ETL Processes**
  - We developed a **star-schema data mart** to hold transformed data suitable for analysis.
  - We defined ETL processes to populate the data mart from the staging area using `Pentaho Data Integration (PDI)`.

- **Part 3: OLAP Cube and Business Analytics**
  - An **OLAP cube** was created using `Pentaho Schema Workbench` to facilitate **complex analytical queries**.
  - We designed and executed both `SQL` and `MDX` queries to answer critical business questions such as **profitability by product categories, revenue by countries, and customer purchasing activities.**


## Schematic overview of OLTP and its corresponding Data Mart

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/data_platform/oltp_schema.png" title="OLTP Schema" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Logical schema of a portion of OLTP System
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/data_platform/data_mart_schema.png" title="Data Mart Schema" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Logical schema of a required data mart database
</div>

## License

This project is licensed under the Apache 2.0 Licence - see the [LICENSE](https://github.com/r-gg/bi-assignments/blob/main/LICENSE) file for details.

> Code available in the [Github repository](https://github.com/r-gg/bi-assignments/tree/main/BI_Projects/BI_40)