---
layout: post
title:  "Literature Study - first findings"
date:   2020-06-30 12:00:55 +0100
author:
  name: Richard Girke - Developer
  twitter: tawalaya
  picture: /images/
categories: posts
---
In the Smile-project, we aim to migrate data processing approaches to serverless. In the course of the project we thus asked the question what reserach and industy have done so far in this field. As a first approach to answering this question, wie performed a grey literature review, based on [this](https://onlinelibrary.wiley.com/doi/epdf/10.1111/ijmr.12102). For the study we defined two reserach questions.
> Q1: What serverless data processing approaches exist in research and industry?

> Q2: What type of processing is done using serverless data processing?

We started our search by searching the most common literature databases namley ACM, IEEE, Springer Link, Elsevier, Google Scholar, Microsoft Academic and our own [Serverless Literature Database](https://www.ise.tu-berlin.de/menue/projekte/benchmarking_faas_platforms). After removing duplicates the search yielded 245 papers. Out of these we selected 76 relevant to our research question.
 


In these papers we could identify 18 frameworks that deal with data processing on serverless platforms out of those 10 made their source code available and were therefore considered for our comparison.


| Name        | Source                                      | Age [^1] | Platform|
|-------------|---------------------------------------------|----------|--------|
| PyWren      | https://github.com/pywren/pywren            | 679      |AWS[^2] |
| IBM PyWren  | https://github.com/pywren/pywren-ibm-cloud  | 11       |ICF[^3] |
| gg          | https://github.com/StanfordSNR/gg           | 102      |AWS[^2] |
|Spark on Lambda|https://github.com/qubole/spark-on-lambda  | 429      |AWS[^2] |
|Marla        | https://github.com/grycap/marla             | 723      |AWS[^2] |
|Ooso         | https://github.com/d2si-oss/ooso            | 1156     |AWS[^2] |
|Wukong       | https://github.com/mason-leap-lab/Wukong    | 305      |AWS[^2]|
|Scar         | https://github.com/grycap/scar              | 35       |AWS[^2] |
|Corral       | https://github.com/bcongdon/corral          | 570      |AWS[^2] |
| Locus       | https://github.com/shivaram/pywren          | 1362     |AWS[^2] |

To answer the second research question we extracted use cases from the relevant papers and categorised them to get an overview of the research directions. 

<figure class="align-center">
  <img src="{{ '/images/use-case-graph.png' | absolute_url }}" alt=""/>
  <figcaption>FaaS-based Data Processing Prototype Categories</figcaption>
</figure> 




[^1]: In days since the last commit
[^2]: Amazon AWS Lambda
[^3]: IBM Cloud Functions
