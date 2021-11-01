Q1

![스크린샷 2021-11-01 오후 8.10.11](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-11-01 오후 8.10.11.png)

- support rapid updates and retrieval of locations
- RDS for PostgreSQL DB instance with read replicas to store
- unable to maintain the performance that is needed for reading and writing updates



D is correct.

The game requires live location tracking of players based ==> ElastiCache for Redis



Q2

![스크린샷 2021-11-01 오후 8.35.08](../Library/Application Support/typora-user-images/스크린샷 2021-11-01 오후 8.35.08.png)

- scans millions of connected devices for security threats and pushes the scan logs to an S3 bucket
- 70GB generated each week
- 3 years of data for historical reporting
- must process aggregate and enrich the data from S3
- S3 performing complex queries and joins the least amount of time



Create and run an ETL job in AWS Glue to process the data from S3 and load it into Redshift Perform the aggregation queries on Amazon Redshift.



Q3

### ![스크린샷 2021-11-01 오후 8.40.42](../Library/Application Support/typora-user-images/스크린샷 2021-11-01 오후 8.40.42.png)

ALB ==> public subnets

EC2 ==> RDS, EC2 in private



Q4

![스크린샷 2021-11-01 오후 8.55.05](../Library/Application Support/typora-user-images/스크린샷 2021-11-01 오후 8.55.05.png)

- upload files to a S3
- files are processed to extract metadata
- less than 5 sec
- concurrent uploads
- CE

The answer is B

S3 events trigger Lamda

Using Lambda to process the file is the best solution as it takes just 5 seconds per process. The best and easiest way to invoke lambda is to use the S3 bucket "create event notification" property and use the "object create" type event. 



Q5

![스크린샷 2021-11-01 오후 9.12.40](../Library/Application Support/typora-user-images/스크린샷 2021-11-01 오후 9.12.40.png)

- multi-region disaster recovery solution
- EC2 instances, RDS, RTO is 3hours and RPO is 24hours
- CE



The answer is D.

read replicas can be done in multiple regions.

but they are not a suitable backup tool but are only used to improve performance

so not B&C

ALB works only within a region ==> not A

So create a snapshot of the RDS instance, and replicate the snapshot for a backup region is the most cost-effective way.



Q6

![스크린샷 2021-11-01 오후 9.21.40](../Library/Application Support/typora-user-images/스크린샷 2021-11-01 오후 9.21.40.png)

The answer is A.

Least amount of downtime ==> not B, C(CloudFormation takes some downtime while executing)

D ==> Manually creating a solution ==> takes more time

DNS failover ==> A



 
