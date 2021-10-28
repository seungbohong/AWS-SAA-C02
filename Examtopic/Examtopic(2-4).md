### 101.
<img width="786" alt="스크린샷 2021-10-29 오전 2 00 17" src="https://user-images.githubusercontent.com/45779378/139301654-c575077d-6084-4d5b-b7a2-cc87578ac351.png">

- EC2 running on a private subnet ==> access a public website
- doesn't want external website to see the EC2 instance IP address or Initiate connections to it



The answer is B.

NAT gateway is a Network Address Translation(NAT) = 네트워크 주소 변환

NAT gateway ==> instances in a private subnet can connect to services outside your VPC but external service cannot initiate a connection with those instances.



### 102.
<img width="787" alt="스크린샷 2021-10-29 오전 2 00 28" src="https://user-images.githubusercontent.com/45779378/139301683-3d28e09f-1858-43bc-8fb1-ea5a0ba0d961.png">

- migrate 20TB of data from a data center to the AWS Cloud within 30days
- network bandwidth is limited to 15 Mbps
- and cannot exceed 70% utilization



The answer is A.

20TB ==> AWS Snowball



### 103.
<img width="755" alt="스크린샷 2021-10-29 오전 2 02 56" src="https://user-images.githubusercontent.com/45779378/139302017-2886f842-a254-4b77-891b-1be8fbf756dc.png">

- EC2 instances across two AZ
- expecting spikes in traffic on specific holidays
- wants to provide a consistent user experience



The answer is D

Expect spikes ==> Scheduled Scaling



### 104.
<img width="793" alt="스크린샷 2021-10-29 오전 2 00 59" src="https://user-images.githubusercontent.com/45779378/139301753-766ac8ff-437c-4d1b-b81c-c96e4991b033.png">

- multi-tier app on AWS
- front-end, backend tiers both run on EC2
- database on RDS for MySQL
- frequent calls to return identical(동일한) datasets ==> cause low performance



The answer is  B.

frequent calls to return identical datasets ==> causing performance slowdowns

same read query is performed over and over again ==> Elasticache



### 105.
<img width="789" alt="스크린샷 2021-10-29 오전 2 01 08" src="https://user-images.githubusercontent.com/45779378/139301777-ce38db98-9a94-463b-b60d-de21e134936b.png">

- on-premises data center that is running out of storage capacity
- migrate to AWS while minimizing bandwidth costs
- must allow for immediate retrieval of data at no additional cost



The answer is B.



A ==> Expedited retrieval within 1-5minutes (No, immediate retrieval)

B ==> Cached volume store data in S3(freeing up localspace) and retain a copy of frequently accessed data locally(immediate retrieval and minimizing bandwidth costs)

C ==> Stored volumes to store ALL your data locally(No, running out of space)

D ==> it's expensive to set up direct connect.

Cached Volumes offer a substantial cost savings on primary storage and minimize the need to scale your storage on-premises.



### 106.
<img width="809" alt="스크린샷 2021-10-29 오전 2 01 17" src="https://user-images.githubusercontent.com/45779378/139301803-56de72a8-f0db-4f1c-acad-93bec094bb7b.png">

- daily basis
- S3, analyzed daily for one week
- must remain immediately accessible for occasional analysis
- The most cost-effective storage solution.



The answer is D

occasional analysis ==> OneZone IA 



### 107.
<img width="798" alt="스크린샷 2021-10-29 오전 2 01 25" src="https://user-images.githubusercontent.com/45779378/139301821-d9c1d688-262b-4de2-8a1f-97730f9bc4fa.png">

- deliever files in S3 to certain users who do not have credentials
- These users must be given access for a limited time



The answer is B.

given access for a limited time ==> Grant-time-limited permissions ==> Presigned URL



### 108.
<img width="794" alt="스크린샷 2021-10-29 오전 2 01 33" src="https://user-images.githubusercontent.com/45779378/139301836-db78d8f9-2d21-4cf2-a4c0-46b41ff28abd.png">

- hybrid workload for data processing
- accessed by on-premises app for local data processing using an NFS protocol
- must be accessible from the AWS Cloud for further analytics and batch processing

==**NFS**는 컴퓨터 사용자가 원격지 컴퓨터에 있는 파일을 마치 자신의 컴퓨터에 있는 것처럼 검색하고, 마음대로 저장하거나 수정하도록 해주는 클라이언트/서버형 응용프로그램입니다==



The answer is A

NFS ==> File Gateway



### 109.
<img width="802" alt="스크린샷 2021-10-29 오전 2 01 42" src="https://user-images.githubusercontent.com/45779378/139301847-6819fb93-fe2c-4832-8562-7c48d96a8570.png">

- sensitive data on S3
- mandate encryption of data before sending it to S3



The answer is D

Server-side: 

S3 Managed Keys (SSE-S3) 

KMS Managed Keys (SSE-KMS) 

Customer Provided Keys (SSE-C)  



Client-side: KMS managed master encryption keys (CSE-KMS) 

Customer managed master encryption keys (CSE-C)



Client-side encryption is the act of encrypting data before sending it to Amazon S3. 

Client side encryption has two options: 1. AWS KMS CMK 2. customer application



### 110.
<img width="796" alt="스크린샷 2021-10-29 오전 2 01 49" src="https://user-images.githubusercontent.com/45779378/139301856-bf9f6762-e333-4c79-bb5e-9f1a61b055f4.png">

- static content from a public website hosted on EC2 instances to an S3 bucket.
- CloudFront distribution will be used to deliver
- EC2 instances restricts access to a limited set of IP ranges
- Access to the static content should be similarly restricted



The answer is A&B.

==restrict-access== 

1. Use signed URLs or Cookies
2.  required to stop anyone be able to access content of S3 via any other means but through CloudFront Distribution  ==> A
3. Restrict access ==> Use AWS WAF web ACLs ==> B
4. Use geo restriction

