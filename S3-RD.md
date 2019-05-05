
http://jayendrapatil.com/aws-redshift/

Youtube: BackSpace Academy
https://www.youtube.com/watch?v=-F13Tm12zKY

Route53
Introduction to Amazon Route 53 Resolver for Hybrid Cloud (NET215)
https://www.youtube.com/watch?v=D1n5kDTWidQ

https://www.youtube.com/watch?v=wCrjMEBcNeo

DNS Demystified: Amazon Route 53, featuring Warner Bros. (NET202)
https://www.youtube.com/watch?v=AAq-DDbFiIE

AWS re:Invent 2014 | (SDD408) Amazon Route 53 Deep Dive: Delivering Resiliency, Minimizing Latency
https://www.youtube.com/watch?v=f9y-T7mQVxs

https://www.youtube.com/watch?v=1jFnSKk5Dwc
Amazon Route 53 - Intro & Lab (Arun Kumar)


ASM Educational Center (ASM)

ELB https://www.youtube.com/watch?v=85dpw73TN5c


=====
S3 FAQ

https://www.slideshare.net/AmazonWebServices/optimizing-costs-in-amazon-s3-creating-cost-efficiencies-w-amazon-s3-storage-classes-introducing-s3-intelligenttiering-stg398r-aws-reinvent-2018


 Amazon S3 Object Lock(AWS electronic storage services)
In Compliance Mode/ Governance Mode

S3 CloudWatch Metrics

S3 Inventory report files be encrypted?


Storage Class Analysis

Object Tag

 label objects that could be used in conjunction with S3 Lifecycle policies to manage transitions, Cross-region replication
control access to objects tagged with specific key-value pairs, allowing you to further secure confidential data for only a select group or user. 

Inventory
 S3 Batch Operations administer your storage operations across many objects, it also manages retries, displays progress, delivers notifications, provides a completion report, and sends events to AWS CloudTrail for all operations performed on your target objects.

Lifecycle policy
You can set a policy for multipart upload expiration, which expires incomplete multipart uploads based on the age of the upload.
 lifecycle transition policy to automatically migrate objects stored in the S3 Standard storage class to the S3

A transition request is charged
 These rules can invisibly lower storage costs and simplify management efforts. These policies also include good stewardship practices to remove objects and attributes that are no longer needed to manage cost and optimize performance.

CRR is configured at the S3 bucket level. You enable a CRR configuration on your source bucket by specifying a destination bucket in a different Region for replication. 
you can establish S3 Cross-Region Replication rules to make direct copies of data into the S3 Glacier storage class in a different region for backup or other purposes, without having to manage data lifecycle policies.
