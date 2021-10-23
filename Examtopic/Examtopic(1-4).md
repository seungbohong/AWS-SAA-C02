### 51.![스크린샷 2021-10-22 오후 8.31.04](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 8.31.04.png)

- EC2 instances stores data in an EBS volume.
- created a second EC2 instance and EBS volume in another AZ with ALB
- could see subset of their documents but never all of the documents at the same time

The answer is **B**

multiple instances ==> EFS is better.

2개의 인스턴스가 같은 set의 데이터에서 작업시에는, EFS가 제공하는 shared file system이 필요함.

하지만 동기화는 어플리케이션에 의해 이뤄짐.



### 52.![스크린샷 2021-10-22 오후 8.30.34](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 8.30.34.png)

- S3 to store images uploaded by its users
- encrypted at rest in Amazon S3
- don't spend time managing and rotation the keys
- but wants to control who can access those keys



D is correct.

SSE-S3: AWS manages both data key and master key 

SSE-KMS: AWS manages data key and you manage master key 

SSE-C: You manage both data key and master key



### 53.

![스크린샷 2021-10-22 오후 8.40.38](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 8.40.38.png)

- E-Commerce on EC2
- stateless web tier that requires minimum of 10 instances and peak of 250 instances to support. 
- The App requires 50 instances 80% of the time
- How to minimize the costs?



The answer is D

계속 50개의 인스턴스를 운용하면 된다 ==> reserved instances for the 50 with mix of On-Demand and Spot instances(spot fleet) to cover the remaining instances.



### 54.

![스크린샷 2021-10-22 오후 10.39.39](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 10.39.39.png)

- API in a VPC behind ALB
- NAT gateway
- request to the client increase ==> NAT gateway costs are higher



The answer is A&D

A : VPC peering connection between the two VPCs, Access the API using the private access

E : With RAM cannot share the API gateway.

D : with PrivateLink I can add the LB



### 55.

![스크린샷 2021-10-22 오후 10.46.45](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 10.46.45.png)

- 750tb transferring filesystem to Amazon S3 Glacier
- must avoid saturating the branch office's low-bandwidth internet connection
- most cost-effective solution?



The answer is D

Snowball available size are 50-80TB



### 56.

![스크린샷 2021-10-22 오후 10.50.36](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 10.50.36.png)

- two-tier app
- EC2 in the public subnet 
- DB runs on the private subnet
- EC2, DB are running in a single AZ
- high-availability for these architecture?



B, E is correct.

for high availability, the Load Balancer and Auto Scailing should span across multiple instances across multipleAZs.



### 57.

![스크린샷 2021-10-23 오전 1.11.41](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 1.11.41.png)

- A3 bucket for storage
- prevent on accidental deletion of the documents and ensure all versions of the docu are available
- can download, modify, upload documents.



to prevent future accidental deletions ==> MFA delete

all versions available ==> keep historical versions of an object ==> versioning



### 58.

![스크린샷 2021-10-23 오전 1.14.51](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 1.14.51.png)

- performance problems
- perform an analysis of the log file to troubleshoot further
- stored on S3 and is 10GB in size
- make the log file available for a limited time.
- What is the most secure way to do this?



secure and available for a limited time ==> presigned URL

A, B는 보안에 취약한 public link를 지원한다 ==> INCORRECT

D는 로그 파일에 엑세스 하는 사용자의 보안에 해당하므로 적합하지 않는다.



presigned URL을 생성하면 자신의 보안자격 증명을 사용하여 개체를 다운로드 할 수 있는 제한된 사용권한을 부여 받음

presigned URL은 지정된 기간 동안만 유효하다.



### 59.

![스크린샷 2021-10-23 오전 1.22.53](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 1.22.53.png)

- two-tier web app
- EC2 in public subnets
- DB tier consists of Microsoft SQL Server running on Amazon EC2 in a private subnet
- Security is a high priority



security group은 유지됨.

0.0.0.0, 443 port ==> web app tier

web sg 1433 ==> sql database tier



### 60.

![스크린샷 2021-10-23 오전 1.26.44](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 1.26.44.png)

- attach IAM policies ==> existing IAM roles to enable faster and agility
- but could attach the existing admin policy

circumvent(우회)

D is correct.

유저, 역할에 바운더리를 정할 수 있다.