
AWS re:Invent 2018: Amazon DynamoDB Deep Dive: Advanced Design Patterns for DynamoDB (DAT401)

https://www.youtube.com/watch?v=HaEPXoXVf2k


Passed the exam (again). My thoughts; ( Ryan Kroonenburg - Exam Blue Print)
https://acloud.guru/forums/aws-certified-solutions-architect-associate/discussion/-JymxnlNfs5fzy796kEd/passed_the_exam_(again)._my_th


BackSpace Academy

https://www.youtube.com/channel/UCav3fsasRc5VOqvZiT5avgw

Auto Scaling service
https://www.youtube.com/watch?v=qOLOhvlpMyU




AutoScaling Strategy/Ability

Redshift
https://aws.amazon.com/about-aws/whats-new/2016/09/amazon-redshift-now-supports-enhanced-vpc-routing/
columnar storage disk memory (1MB block size()

Enhanced VPC Routing is required for Redshift to access S3 VPC endpoint.

Lifecycle hooks to avoid data loss & copy data before 

Cooldown period to complete custom actions before instance terminates

customise Termination policy to complete data copy before termination (is used to specify which instances to terminate first during scale in)

https://docs.aws.amazon.com/autoscaling/ec2/userguide/Cooldown.html
https://docs.aws.amazon.com/autoscaling/ec2/userguide/lifecycle-hooks.html

autoscaling/ec2/faqs/

https://aws.amazon.com/blogs/aws/new-ec2-auto-scaling-groups-with-multiple-instance-types-purchase-options/
https://docs.aws.amazon.com/autoscaling/ec2/userguide/AutoScalingGroup.html#asg-purchase-options


https://docs.aws.amazon.com/amazonglacier/latest/dev/downloading-an-archive-two-steps.html



NAT gateway up to 45Gbps, and depends on instance type.


https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.html

replica less than 100ms, grow up to 10TB in size, 4 replica (quadruple in terms of size)



Elastic BeanStalk
https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts-webserver.html
https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts-worker.html

HDD EBS
Minimul volume of Throughput-optimised SSD is 500GB


Auora (schema change)

Redshift Encryption hierarchy





https://aws.amazon.com/blogs/aws/new-automatic-cost-optimization-for-amazon-s3-via-intelligent-tiering/
