### 111.
<img width="824" alt="스크린샷 2021-10-30 오후 10 51 46" src="https://user-images.githubusercontent.com/45779378/139535589-3b79d6b3-c9aa-432b-a3f3-a228d35ee049.png">

- collect, process, store user's service usage data
- enable the company to gather operational insights quickly using standard  SQL queries
- HA, ensure Atomicity, Consistency, Isolation and Durability (ACID)



The solution is C

ACID ==> RDS, DynamoDB

but SQL ==> RDS only(DynamoDB is No SQL DB)



### 112.
<img width="798" alt="스크린샷 2021-10-30 오후 10 51 55" src="https://user-images.githubusercontent.com/45779378/139535594-afa5d13b-45d4-436c-af4b-16fbd48cd79a.png">

- server content to global
- store and accelerate the delivery of static content to its users by leveraging CloudFront with EC2
- HA



The answer is C.

How to improve HA ==> current only EC2 instance in single AZ ==> Multi AZ with another EC2



### 113.
<img width="813" alt="스크린샷 2021-10-30 오후 10 52 13" src="https://user-images.githubusercontent.com/45779378/139535605-e9fd2e6f-bb51-4c49-8c40-569e6ab4372d.png">

- EC2 instance in VPC-A needs to access files in another EC2 instance in VPC-B

- Both are in separete accounts

- enable secure access to EC2 instance in VPC-B from VPC-A

- should not have a single point of failure or bandwidth concerns

  

The answer is A



You can establish peering relationships between VPCs across different AWS Regions (also called Inter-Region VPC Peering). This allows VPC resources including EC2 instances, Amazon RDS databases and Lambda functions that run in different AWS Regions to communicate with each other using private IP addresses, without requiring gateways, VPN connections, or separate network appliances. The traffic remains in the private IP space. All inter-region traffic is encrypted with no single point of failure, or bandwidth bottleneck.



VPC peering works in separate aws accounts.

Private VIF works only in same aws account.



### 114.
<img width="758" alt="스크린샷 2021-10-30 오후 10 53 07" src="https://user-images.githubusercontent.com/45779378/139535655-951d3237-bbe8-48da-9488-69431951dc78.png">

-  symmetric encryption keys in a HSM(Hardware Security Module)
- migrate key management to AWS
- allow for key rotation and support the use of customer provided keys



The answer is D.

KMS ==> Manages all the keys to encrypt/decrypt stuff

Secrets Manager ==> Manages passwords that are encrypted with KMS.

HSM contains encryption keys not password

So it's D.



### 115.
<img width="794" alt="스크린샷 2021-10-30 오후 10 52 29" src="https://user-images.githubusercontent.com/45779378/139535622-1691eb78-bf08-4051-9446-2e1b4ead0ef9.png">

- reduce backup costs
- simplify the on-premises backup infra and reduce costs by elimination the use of physical backup tapes
- preserve the existing investment in the on-premises backup



The answer is D.

Tape Gateway enables you to replace using physical tapes on premises with virtual tape in AWS without changing existing backup workflows.



### 116.
<img width="791" alt="스크린샷 2021-10-30 오후 10 53 21" src="https://user-images.githubusercontent.com/45779378/139535667-246c612e-4495-4bd6-91f1-92e048ae40b5.png">

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
<img width="792" alt="스크린샷 2021-10-30 오후 10 53 29" src="https://user-images.githubusercontent.com/45779378/139535676-8bb74ffb-924d-42a8-8ca5-77bd439f2d4d.png">

- EC2 instances needs to access an S3
- traffic cannot traverse the internet



The answer is B.

Since PrivateLink is between a VPC and another resource.

and here assuming it is all in same VPC

So go for B.



### 118.
<img width="805" alt="스크린샷 2021-10-30 오후 10 53 37" src="https://user-images.githubusercontent.com/45779378/139535682-45f61868-f0af-48e2-afae-d0ed4ef4fa47.png">

- read the files with low latency
- migrate to AWS
- process a large set of files ==by accessing the same files at the same time.==



The answer is D.

concurrent access ==> EFS



### 119.
<img width="791" alt="스크린샷 2021-10-30 오후 10 53 45" src="https://user-images.githubusercontent.com/45779378/139535688-91578048-4138-4e3e-9906-1a79e0674e7b.png">

- RDS based ==> performance degradation
- read-only SQL queries triggered



The answer is C.

RDS performance slow ==> Read replica!!!



### 120.
<img width="800" alt="스크린샷 2021-10-30 오후 10 53 51" src="https://user-images.githubusercontent.com/45779378/139535692-8693fe38-5ca3-4ea2-8aa0-6ddbc6ec7a86.png">

- EC2, RES
- PII(personally identifiable information) be encrypted at rest.
- Least amount of changes to the infra?



The answer is D

backed by managed

D seems to the right option as it will encrypt both the EC2 EBS volume and also the RDS database.



