Q1
<img width="719" alt="스크린샷 2021-11-01 오후 9 43 02" src="https://user-images.githubusercontent.com/45779378/139673271-6287c69a-aabd-4c2d-bab6-6ceb1f4790c3.png">

- support rapid updates and retrieval of locations
- RDS for PostgreSQL DB instance with read replicas to store
- unable to maintain the performance that is needed for reading and writing updates



D is correct.

The game requires live location tracking of players based ==> ElastiCache for Redis



Q2
<img width="715" alt="스크린샷 2021-11-01 오후 9 43 11" src="https://user-images.githubusercontent.com/45779378/139673288-d5bf4e6d-4bbf-4811-9cbe-f4bf23dd322e.png">

- scans millions of connected devices for security threats and pushes the scan logs to an S3 bucket
- 70GB generated each week
- 3 years of data for historical reporting
- must process aggregate and enrich the data from S3
- S3 performing complex queries and joins the least amount of time



Create and run an ETL job in AWS Glue to process the data from S3 and load it into Redshift Perform the aggregation queries on Amazon Redshift.



Q3
<img width="680" alt="스크린샷 2021-11-01 오후 9 43 28" src="https://user-images.githubusercontent.com/45779378/139673327-6ba8c7e2-08b9-47f2-8ced-dc66b5086fb1.png">

ALB ==> public subnets

EC2 ==> RDS, EC2 in private



Q4
<img width="726" alt="스크린샷 2021-11-01 오후 9 43 37" src="https://user-images.githubusercontent.com/45779378/139673345-b9f13d54-867b-45a2-a7c3-ce63f469f2cd.png">

- upload files to a S3
- files are processed to extract metadata
- less than 5 sec
- concurrent uploads
- CE

The answer is B

S3 events trigger Lamda

Using Lambda to process the file is the best solution as it takes just 5 seconds per process. The best and easiest way to invoke lambda is to use the S3 bucket "create event notification" property and use the "object create" type event. 



Q5
<img width="725" alt="스크린샷 2021-11-01 오후 9 43 46" src="https://user-images.githubusercontent.com/45779378/139673360-fee2e8d5-8575-4bd1-8a74-40cfc42c73e7.png">

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
<img width="721" alt="스크린샷 2021-11-01 오후 9 43 55" src="https://user-images.githubusercontent.com/45779378/139673378-0a497072-e665-413c-a28b-0ad4c808f406.png">

The answer is A.

Least amount of downtime ==> not B, C(CloudFormation takes some downtime while executing)

D ==> Manually creating a solution ==> takes more time

DNS failover ==> A



 
