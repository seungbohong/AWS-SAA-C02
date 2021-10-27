### 91.
<img width="607" alt="스크린샷 2021-10-27 오후 4 56 35" src="https://user-images.githubusercontent.com/45779378/139024136-74c74a51-c778-4aa6-a73c-0d7564fb988f.png">

- requests by some suspicious IP address
- different IP addresses under the same CIDR range



The answer is C.

Add a deny rule in the inbound table of the network ACL with a lower number than other rules.

==> You can only create rules with network ACLs

inbound table = 외부로 부터의 테이블

outbound traffic = 내부로 부터의 테이블

외부의 malicious IP 등록 ==> deny rule in the inbound table



### 92.
<img width="618" alt="스크린샷 2021-10-27 오후 4 57 19" src="https://user-images.githubusercontent.com/45779378/139024276-b5ce5a84-aa3d-4d1e-bde3-a80912c306b7.png">

- make it app accessible to users in those geographic locations
- Scalable
- ability shift traffic from resources in one region to another



The answer is C

shift traffic from resources in one region to another ==> geoproximity routing policy

==Geoproximity VS Geolocation==

- Geoproximity Routing ==> 자원들의 위치에 기반하여 route traffic 또한 shift traffic from resources in one location to another resources.

- Geolocation Routing ==> 유저의 위치에 기반하여 route traffic



### 93.
<img width="609" alt="스크린샷 2021-10-27 오후 4 57 04" src="https://user-images.githubusercontent.com/45779378/139024222-cd787eaa-2ec1-45ce-a53a-b4e39c8b5117.png">


- replicate its data to AWS to recover in the event of disaster ==> on-premise
- copy data to a NFS share
- bakup files with low latency



Low latency access from on-premise is required ==> Storage File Gateway



### 94.
<img width="611" alt="스크린샷 2021-10-27 오후 4 57 34" src="https://user-images.githubusercontent.com/45779378/139024325-3f432b27-be17-45fd-bbb2-f075ee4e2117.png">

- stored for 7 years
- on premises, managed service to transfer the files to AWS storage



transfer the files in on-premise ==> AWS Storage Gateway

The answer is D.



### 95.
<img width="616" alt="스크린샷 2021-10-27 오후 4 58 26" src="https://user-images.githubusercontent.com/45779378/139024476-5199c9db-6e79-40c1-ba31-ed2260e4b566.png">

- EC2 Linux instances in a VPC
- use a hierarchical directory structure
- rapid and concurrently read and write to shared storage



use hierarchical directory structure ==> Elastic File System.



### 96.
<img width="613" alt="스크린샷 2021-10-27 오후 4 58 39" src="https://user-images.githubusercontent.com/45779378/139024502-c545b8e6-ff3d-45a4-b20f-af091966d196.png">

- a nightly batch processing job is automatically scaled up for 1 hour before the desired EC2 capacity is reached
- peak capacity is the same
- batch jobs always start at 1 AM.
- cost-effective solution which will allow for the desired EC2 capacity to be reached quickly and allow ASG to scale down after the batch jobs are complete



The answer is C

The peak capacity is the same every night and the batch jobs always start at 1AM ==> Predictable nature of workload ==> Scheduled scailing to scale up to the desired compute level



### 97.
<img width="623" alt="스크린샷 2021-10-27 오후 4 58 51" src="https://user-images.githubusercontent.com/45779378/139024545-cfb2d4c1-aad9-4011-9b6d-0dbaec766eb1.png">

- hosted on AWS, allowing users to purchase access to premium, shared content that is stored in a S3 bucket.
- on payment, content will be available for download for 14days
- Least complicated implementation?



hosted on AWS, allowing users to purchase access to premium, shared content that is stored in a S3 bucket. ==> CloudFront distribution with an OAI.

able to download for 14days ==> set an expiration of 14days for the URL



The answer is C.



### 98.
<img width="597" alt="스크린샷 2021-10-27 오후 4 59 04" src="https://user-images.githubusercontent.com/45779378/139024577-5973a904-82b9-4508-8f83-11e93f3e5dc5.png">

- Scalable
- DB should be HA and also fault tolerant



HA ==> Multi-AZ

Scalable ==> RDS, MySQL



The answer is D, E

A : Redshift is a cloud data warehouse not a sql database

B : it does not say that global tables are active and it is a NoSQL database.

C : ==it is not multi az==



### 99.
<img width="623" alt="스크린샷 2021-10-27 오후 4 59 16" src="https://user-images.githubusercontent.com/45779378/139024601-f4187c92-a68e-4a4c-8759-0cfdedb4f8af.png">

- Scalable
- recently changed company's policy
- requires to be accessed from one specific country only



The answer is C.

 scalable ==> WAF



### 100.
<img width="610" alt="스크린샷 2021-10-27 오후 4 59 28" src="https://user-images.githubusercontent.com/45779378/139024624-eda301ce-6cce-4650-9f27-292f963054e3.png">
<img width="599" alt="스크린샷 2021-10-27 오후 4 59 37" src="https://user-images.githubusercontent.com/45779378/139024648-9cd33eb3-659e-4404-a0d5-4d47c21ba78e.png">

- Cloud engineer : IAM user to the IAM group
- what action will be able to perform?



The answer is C

allow ec2:* means EC2 instances can be deleted.
