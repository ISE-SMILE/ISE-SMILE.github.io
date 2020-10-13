---
layout: post
title:  "Serverless Data Processing a Multivocal Literature Study"
date:   2020-06-30 12:00:55 +0100
author:
  name: Richard Girke - Developer
  links:
    - title: GitHub
      url: https://github.com/dergeh
      icon: fab fa-github
categories: posts
---
In the Smile-project, we aim to migrate data processing approaches to serverless computing. In the course of the project, we asked what research and industry have done so far in this field. As a first approach to answering this question, we performed a multi-vocal literature review, based on this paper[^6]. For the study, we defined two research questions:
> Q1: What serverless data processing approaches exist in research and industry?

> Q2: What use-cases and purposes for serverless data processing are currently investigated?

We started our search by searching the most common literature databases, namely ACM, IEEE, Springer Link, Elsevier, Google Scholar, Microsoft Academic, and our own [Serverless Literature Database](https://www.ise.tu-berlin.de/menue/projekte/benchmarking_faas_platforms). After removing duplicates, the search yielded 245 papers. Out of these, we selected 76 relevant to our research question.
 
In these papers, we extracted 18 serverless data processing approaches. Out of those, ten made their source code available. 


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

What first catches the eye is the fact that almost all frameworks use AWS Lambda as their backend. Amazon being the first to launch a commercially available FaaS platform, could be a reason for this. Only IBM PyWren uses the IBM Cloud Functions as their backend for obvious reasons. We identified two kinds of tools supporting data processing: data transformation framework (DTF) and processing platforms (P).  Data transformation frameworks enable data analysts to define jobs in terms of simplified interfaces. The DTF then managed part of the deployment and execution of each data transformation job. Notably, all DTFs share a similar approach to overcome challenges posed by the FaaS environment, such as intermediate data handling and intra-process communication by, for instance, using an intermediate cloud storage for these communications. Most offer a map or map-reduce abstraction to define transformation.
In contrast, processing platforms are tackling these challenges with a more general approach. For example, SCAR offers a solution to deploy custom Docker containers on top of AWS Lambda and scale them faster than comparable Container-as-a-Service solutions. However, these processing platforms offer no specific tools for data transformation. 
Regardless of the type of framework, we noticed that the age of these frameworks varies a lot. One reason could be that most of these frameworks are not used actively outside of research purposes. Only some such as IBM PyWren, recently renamed to lithops, seems to be under very active development since 2018.


To answer the second research question, we extracted use cases from the relevant papers and categorized them to get an overview of the research directions. 

<figure class="align-center">
  <img src="{{ '/images/use-case-graph.png' | absolute_url }}" alt=""/>
  <figcaption>Fig. 1 FaaS-based Data Processing Prototype Categories per publication year</figcaption>
</figure> 
The most common use-case we found was batch data analytics a traditional field in data processing. Data encoding is the second most common use case often used for video encoding or image recogintion in videos. Stream Data Analytics is used for real time data analytics such as mobile device event streams. Operations Automation is a rather small field of reaasearch but interesting for huge distributed compiling and automatic incedence response.



[^1]: In days since the last commit
[^2]: Amazon AWS Lambda
[^3]: IBM Cloud Functions
[^4]: Data Transformation Framework
[^5]: Processing Platform
[^6]: https://onlinelibrary.wiley.com/doi/epdf/10.1111/ijmr.12102


