---
layout: post
title:  "Literature Study - first findings"
date:   2020-06-30 12:00:55 +0100
author:
  name: Richard Girke - Developer
  twitter: 
  picture: /images/
categories: posts
---
In the Smile-project, we aim to migrate data processing approaches to serverless. In the course of the project we thus asked the question what reserach and industy have done so far in this field. As a first approach to answering this question, we performed a grey literature review, based on this paper[^6]. For the study we defined two reserach questions.
> Q1: What serverless data processing approaches exist in research and industry?

> Q2: What type of processing is done using serverless data processing?

We started our search by searching the most common literature databases namley ACM, IEEE, Springer Link, Elsevier, Google Scholar, Microsoft Academic and our own [Serverless Literature Database](https://www.ise.tu-berlin.de/menue/projekte/benchmarking_faas_platforms). After removing duplicates the search yielded 245 papers. Out of these we selected 76 relevant to our research question.
 


In these papers we could identify 18 frameworks that deal with data processing on serverless platforms out of those 10 made their source code available and were therefore considered for our comparison.


| Name        | Source                                             | Age [^1] | Platform|Kind|
|-------------|----------------------------------------------------|----------|---------|
| PyWren      | [git](https://github.com/pywren/pywren)            | 679      |AWS[^2]  |DTF[^4]|
| IBM PyWren  | [git](https://github.com/pywren/pywren-ibm-cloud)  | 11       |ICF[^3]  |DTF|
| gg          | [git](https://github.com/StanfordSNR/gg )          | 102      |AWS      |DTF|
|Spark on Lambda|[git](https://github.com/qubole/spark-on-lambda)  | 429      |AWS      |DTF|
|Marla        | [git](https://github.com/grycap/marla)             | 723      |AWS      |DTF|
|Ooso         | [git](https://github.com/d2si-oss/ooso)            | 1156     |AWS      |DTF|
|Wukong       | [git](https://github.com/mason-leap-lab/Wukong)    | 305      |AWS      |DTF|
|Scar         | [git](https://github.com/grycap/scar)              | 35       |AWS      |P[^5]|
|Corral       |[git](https://github.com/bcongdon/corral)           | 570      |AWS      |DTF| 
| Locus       |[git](https://github.com/shivaram/pywren)           | 1362     |AWS      |DTF|

What first catches the eye is the fact that almost all frameworks use AWS Lambda as their backend. Amazon being the firsdt to launch a comerical available FaaS platform could be a reason for this. Only IBM PyWren uses the IBM Cloud Functions as their backend for obvious reasons. We indentified two types of frameworks data transformation frameworks (DTF) and platforms (P). DTFs share a similar approach to overcome challenges posed by the FaaS environment such as intermediate data handling and intra process communication by using an intermediate cloud storage for these communications. They all offer some kind of map or map-reduce functionality and handle the deployment on the faas backend. Whereas platforms are tackling these challanges with a more general approach. SCAR for example offers a solution to deploy custom docker container on AWS Lambda and helps to scale them faster but offers no specific tools for data transformation. 
What also comes to mind when looking at the ages of these frameworks is a huge diffrence in actuality. This measure was also considered for our future work.


To answer the second research question we extracted use cases from the relevant papers and categorised them to get an overview of the research directions. 

<figure class="align-center">
  <img src="{{ '/images/use-case-graph.png' | absolute_url }}" alt=""/>
  <figcaption>Fig. 1 FaaS-based Data Processing Prototype Categories per publication year</figcaption>
</figure> 
The most common use-case we found was batch data analytics a traditional field in data processing. Data encoding is the second most common use case often used for video encoding or image recogintion in videos. Stream Data Analytics is used for real time data analytics such as mobile device event streams. Operations Automation is a rather small field of reaasearch but interesting for huge distributed compiling.



[^1]: In days since the last commit
[^2]: Amazon AWS Lambda
[^3]: IBM Cloud Functions
[^4]: Data Transformation Framework
[^5]: Platform
[^6]: https://onlinelibrary.wiley.com/doi/epdf/10.1111/ijmr.12102


