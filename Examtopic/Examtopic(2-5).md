### 111.

![스크린샷 2021-10-30 오후 9.47.12](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-30 오후 9.47.12.png)

- collect, process, store user's service usage data
- enable the company to gather operational insights quickly using standard  SQL queries
- HA, ensure Atomicity, Consistency, Isolation and Durability (ACID)



The solution is C

ACID ==> RDS, DynamoDB

but SQL ==> RDS only(DynamoDB is No SQL DB)



### 112.

![스크린샷 2021-10-30 오후 9.51.30](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-30 오후 9.51.30.png)

- server content to global
- store and accelerate the delivery of static content to its users by leveraging CloudFront with EC2
- HA



The answer is C.

How to improve HA ==> current only EC2 instance in single AZ ==> Multi AZ with another EC2



### 113.

![스크린샷 2021-10-30 오후 9.57.09](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-30 오후 9.57.09.png)

- EC2 instance in VPC-A needs to access files in another EC2 instance in VPC-B

- Both are in separete accounts

- enable secure access to EC2 instance in VPC-B from VPC-A

- should not have a single point of failure or bandwidth concerns

  

The answer is A



You can establish peering relationships between VPCs across different AWS Regions (also called Inter-Region VPC Peering). This allows VPC resources including EC2 instances, Amazon RDS databases and Lambda functions that run in different AWS Regions to communicate with each other using private IP addresses, without requiring gateways, VPN connections, or separate network appliances. The traffic remains in the private IP space. All inter-region traffic is encrypted with no single point of failure, or bandwidth bottleneck.



VPC peering works in separate aws accounts.

Private VIF works only in same aws account.



### 114.

![스크린샷 2021-10-30 오후 10.04.19](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-30 오후 10.04.19.png)

-  symmetric encryption keys in a HSM(Hardware Security Module)
- migrate key management to AWS
- allow for key rotation and support the use of customer provided keys



The answer is D.

KMS ==> Manages all the keys to encrypt/decrypt stuff

Secrets Manager ==> Manages passwords that are encrypted with KMS.

HSM contains encryption keys not password

So it's D.



### 115.

![스크린샷 2021-10-30 오후 10.16.31](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-30 오후 10.16.31.png)

- reduce backup costs
- simplify the on-premises backup infra and reduce costs by elimination the use of physical backup tapes
- preserve the existing investment in the on-premises backup



The answer is D.

Tape Gateway enables you to replace using physical tapes on premises with virtual tape in AWS without changing existing backup workflows.



### 116.

![스크린샷 2021-10-30 오후 10.26.04](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-30 오후 10.26.04.png)

- an EC2 instance that requires a maximum of 200GB storage space.
- used infrequently, with peaks during mornings and evenings.
- Disk I/O varies a 3000IOPS
- cost-effective storage option that does not sacrifice performance



B is correct.

Cold HDD(sc1) & Throughput Optimized HDD(st1) volume must be 500GB at least ==> Eliminate A&D

IO1 is more expensive than GP2 ==> Eliminate C

200GB of GP2 gives baseline of 200*3=600IOPS and burstable to 3000IOPS

GP2 supports up to 16,000 IOPS.



### 117.

![스크린샷 2021-10-30 오후 10.32.04](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-30 오후 10.32.04.png)

- EC2 instances needs to access an S3
- traffic cannot traverse the internet



The answer is B.

Since PrivateLink is between a VPC and another resource.

and here assuming it is all in same VPC

So go for B.



### 118.

![스크린샷 2021-10-30 오후 10.34.48](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-30 오후 10.34.48.png)

- read the files with low latency
- migrate to AWS
- process a large set of files ==by accessing the same files at the same time.==



The answer is D.

concurrent access ==> EFS



### 119.

![스크린샷 2021-10-30 오후 10.42.14](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-30 오후 10.42.14.png)

- RDS based ==> performance degradation
- read-only SQL queries triggered



The answer is C.

RDS performance slow ==> Read replica!!!



### 120.

![스크린샷 2021-10-30 오후 10.43.36](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-30 오후 10.43.36.png)

- EC2, RES
- PII(personally identifiable information) be encrypted at rest.
- Least amount of changes to the infra?



The answer is D

backed by managed

D seems to the right option as it will encrypt both the EC2 EBS volume and also the RDS database.



