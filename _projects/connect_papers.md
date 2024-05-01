---
layout: page
title: connect-papers
description: Scraping ResearchGate for citation-relationships and visualizing them
img: assets/img/connect-papers/graph.png
# redirect: https://unsplash.com
importance: 1
category: fun
---
**Keywords:** *python, webscraping, selenium webdriver, pyvis*

While doing research for the Performance isolation paper, I was inspired to make a tool for visualizing references between the research papers. After implementing the first prototype I found out there are already plenty of advanced commercial solutions supporting this. 😅 

To achieve this, I implemented a ResearchGate scraper that would take a list of papers and build a **set** of their citation-relationships as well as extend these with citations up to depth *d*. These relationships were then visualized in form of an interactive undirected [graph](https://r-gg.github.io/assets/html/graph.html). 

> Code available in the [GitHub repository](https://github.com/r-gg/connect-papers/).

> A demo of the resulting graph is available [here](https://r-gg.github.io/assets/html/graph.html).


Here is also a screenshot of the references graph:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/connect-papers/site.png" title="Citation graph" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Screenshot of the citation graph.
</div>