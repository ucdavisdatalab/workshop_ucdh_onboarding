# Amazon Web Services (AWS)
The hospital has a contract with Amazon to provide Amazon Web Services (AWS) to UCDH researchers. AWS uses datacenters and compute servers in the cloud and is therefore useful for working with data or methods that exceed the capacity of UCDH-owned hardware. 

AWS is an extraordinarily powerful tool built for enterprise-tier data science. In digital services, the term "enterprise" refers to the scale of big public companies like the S&P 500. Providing services on such a scale requires storing and processing massive data sets, as well as mitigating security risks, whether malicious or inadvertent. These concerns are generally less relevant for individuals or small research groups but if you are going to make use of AWS you will need to accept that it works very differently from your personal computer.

The services provided by AWS are quite specialized, so to do a specific task may require knowing the name of a specific service of AWS, and the services tend to have separate and incompatible jargon. The most relevant services are probably data storage with Simple Storage Service (S3) and analysis with SageMaker, Elastic Compute Cloud (EC2), or DataBricks.

## Get Access
Before learning to use AWS, you will need to establish an account. Begin by connecting to the UCDH AWS at [ucdh.awsapps.com/start/#](ucdh.awsapps.com/start/#).

## Data Storage With S3
In order to do any data science on AWS, you will need to make sure your data is accessible in your analysis or modeling workflow. S3 is Amazon's service for storing data in AWS. S3 works differently than file systems like you have used on your personal computer. In particular, there is no overall hierarchy to the file system that can be used to locate files. Instead, data is stored in S3 **buckets**, which are kept separate from each other. Within each bucket, the data are stored as **objects** and objects can be organized to simulate a hierarchical file system but that breaks down when working between buckets.

Each object has a **key** that identifies it within its bucket. The key must be unique within the bucket but not between buckets. Therefore, you must know both the key and the bucket in order to identify a particular data object in S3.

## SageMaker
SageMaker is a service that can provide a simulated computer environment on AWS. For instance, you may use SageMaker to get an interface that looks to the user like a Linux desktop with a filesystem and a console. This is a convenient environment for writing analyses and running prototype versions.

## Elastic Compute Cloud (EC2)
