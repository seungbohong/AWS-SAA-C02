### 91.

![스크린샷 2021-10-27 오전 9.51.02](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 9.51.02.png)

- requests by some suspicious IP address
- different IP addresses under the same CIDR range



The answer is C.

Add a deny rule in the inbound table of the network ACL with a lower number than other rules.

==> You can only create rules with network ACLs

inbound table = 외부로 부터의 테이블

outbound traffic = 내부로 부터의 테이블

외부의 malicious IP 등록 ==> deny rule in the inbound table



### 92.

![스크린샷 2021-10-27 오전 9.56.47](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 9.56.47.png)

- make it app accessible to users in those geographic locations
- Scalable
- ability shift traffic from resources in one region to another



The answer is C

shift traffic from resources in one region to another ==> geoproximity routing policy

==Geoproximity VS Geolocation==

- Geoproximity Routing ==> 자원들의 위치에 기반하여 route traffic 또한 shift traffic from resources in one location to another resources.

- Geolocation Routing ==> 유저의 위치에 기반하여 route traffic



### 93.

![스크린샷 2021-10-27 오전 10.03.50](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 10.03.50.png)

- replicate its data to AWS to recover in the event of disaster ==> on-premise
- copy data to a NFS share
- bakup files with low latency



Low latency access from on-premise is required ==> Storage File Gateway



### 94.

![스크린샷 2021-10-27 오후 2.36.22](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오후 2.36.22.png)

- stored for 7 years
- on premises, managed service to transfer the files to AWS storage



transfer the files in on-premise ==> AWS Storage Gateway

The answer is D.



### 95.

![스크린샷 2021-10-27 오후 2.38.54](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오후 2.38.54.png)

- EC2 Linux instances in a VPC
- use a hierarchical directory structure
- rapid and concurrently read and write to shared storage



use hierarchical directory structure ==> Elastic File System.



### 96.

![스크린샷 2021-10-27 오후 2.40.53](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오후 2.40.53.png)

- a nightly batch processing job is automatically scaled up for 1 hour before the desired EC2 capacity is reached
- peak capacity is the same
- batch jobs always start at 1 AM.
- cost-effective solution which will allow for the desired EC2 capacity to be reached quickly and allow ASG to scale down after the batch jobs are complete



The answer is C

The peak capacity is the same every night and the batch jobs always start at 1AM ==> Predictable nature of workload ==> Scheduled scailing to scale up to the desired compute level



### 97.

![스크린샷 2021-10-27 오후 4.10.27](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오후 4.10.27.png)

- hosted on AWS, allowing users to purchase access to premium, shared content that is stored in a S3 bucket.
- on payment, content will be available for download for 14days
- Least complicated implementation?



hosted on AWS, allowing users to purchase access to premium, shared content that is stored in a S3 bucket. ==> CloudFront distribution with an OAI.

able to download for 14days ==> set an expiration of 14days for the URL



The answer is C.



### 98.

![스크린샷 2021-10-27 오후 4.14.44](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오후 4.14.44.png)

- Scalable
- DB should be HA and also fault tolerant



HA ==> Multi-AZ

Scalable ==> RDS, MySQL



The answer is D, E

A : Redshift is a cloud data warehouse not a sql database

B : it does not say that global tables are active and it is a NoSQL database.

C : ==it is not multi az==



### 99.

![스크린샷 2021-10-27 오후 4.21.06](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오후 4.21.06.png)

- Scalable
- recently changed company's policy
- requires to be accessed from one specific country only



The answer is C.

 scalable ==> WAF



### 100.

![스크린샷 2021-10-27 오후 4.46.04](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오후 4.46.04.png)

![스크린샷 2021-10-27 오후 4.46.15](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오후 4.46.15.png)

- Cloud engineer : IAM user to the IAM group
- what action will be able to perform?



The answer is C

allow ec2:* means EC2 instances can be deleted.