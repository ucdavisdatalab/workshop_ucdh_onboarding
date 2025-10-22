# Amazon Web Services (AWS)
Amazon Web Services (AWS) is a collection of services for data science that are optimized for working on very large datasets. The hospital has a contract with Amazon to provide AWS to UCDH researchers as a tool called the **AWS HIPAA Landing Zone**.

AWS is an extraordinarily powerful tool built for enterprise-tier data science. In digital services, the term "enterprise" refers to the scale of big public companies like the S&P 500. Providing services on such a scale requires storing and processing massive data sets, as well as mitigating security risks, both malicious and inadvertent. These concerns are generally less relevant for individuals or small research groups but if you are going to make use of AWS you will need to accept that it works very differently from your personal computer. 

## Cost
The business model of AWS is that users pay to share a pool of computing resources. Thus, your processor and data storage are rented rather than owned. AWS charges by the hour. You incur charges for having a processor reserved, even if you don't end up using it. That's why professional applications that run on AWS are built to activate processors when needed and return them to the pool immediately after. This, in turn, has consequences for how you use tools in AWS. It's generally not a great idea to fire up the most powerful GPU compute node and spend hours interactively programming on it. You would do better to develop and test a model on a low-cost compute node or your personal computer, and then package it in a way that can be used on demand.

The services provided by AWS are quite specialized, so to do a specific task may require knowing the name of a specific service of AWS, and the services tend to have separate and incompatible jargon. The most relevant services are probably data storage with Simple Storage Service (S3) and analysis with SageMaker, Elastic Compute Cloud (EC2), or DataBricks.

## Get Access
Before learning to use AWS, you will need to establish an account. Begin by connecting to the UCDH AWS at [ucdh.awsapps.com/start/#](https://ucdh.awsapps.com/start/#).

## Data Storage With S3
In order to do any data science on AWS, you will need to make sure your data is accessible in your analysis or modeling workflow. S3 is Amazon's service for storing data in AWS. S3 works differently than file systems like you have used on your personal computer. In particular, there is no overall hierarchy to the file system that can be used to locate files. Instead, data is stored in S3 **buckets**, which are kept separate from each other. Within each bucket, the data are stored as **objects** and objects can be organized to simulate a hierarchical file system but that breaks down when working between buckets.

Each object has a **key** that identifies it within its bucket. The key must be unique within the bucket but not between buckets. Therefore, you must know both the key and the bucket in order to identify a particular data object in S3.

## SageMaker
SageMaker is a service that provides an interactive computing environment on AWS. This is a convenient environment for writing analyses and running prototype versions. The 

## Elastic Compute Cloud (EC2)
Elastic Compute Cloud (EC2) runs scripted analyses on hardware that it reserves only while the analysis is running. This is a very cost-efficient way to do computation because you don't have to buy servers or pay for unused server time. The service scales (or stretches, hence "elastic") the available hardware to meet the immediate demand. AWS uses auto-scaling to add new compute nodes to the cluster as needed to handle new requests.

The problem with EC2 is that the value it provides by efficient use of computational hardware is generally less than the cost of your time to learn the system and adapt your code to spin up EC2 servers just for the most intensive part of the computation. EC2 is an example of a service where the overhead of designing for the enterprise scale means it is not useful for small research teams.

## Databricks
In order for a typical researcher or small team to make use of EC2, they need a layer that automates EC2 configuration and control in response to demand from the analysis side. That layer is **Databricks**. If you truly need the power of EC2, then Databricks will save you a ton of time learning how to use EC2 and integrate it with your analysis. The user then focuses on writing R or Python code in a notebook to run their analysis.

UCDH 
