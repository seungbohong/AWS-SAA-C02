### 28.

![스크린샷 2021-10-20 오후 11.36.02](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-20 오후 11.36.02.png)

- 분석 데이터 저장해옴 RDS instance에다가.
- API를 사용해서 사용자들이 접근할수 있도록 함
- 비동작하는 기간은 있지만 수많은 트래픽을 수초내에 진행해야 한다.
- 이때 적합한 솔루션은?



C is the Answer.

Lambda는 수평으로 늘어나기 때문에 리퀘스트가 폭증해도 관리할 수 있다.

또한 cost-effective하다.



### 29.

![스크린샷 2021-10-21 오전 12.09.43](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 12.09.43.png)

- 매월초에 영업 리포트를 만들어야 함
- 20개의 ec2 인스턴스들을 실행한다.
- 7일동안 운영되며 방해받지 않는다.
- 비용 최소화 하고 싶어함



D is the Answer.

Scheduled Reserved Instances는 매일, 매주, 매월로 예약을 가능하게 한다. 특정한 시간대도.

Reserved Instances는 정기적으로 운영되야 하므로 불가능하다.



### 30.

![스크린샷 2021-10-21 오전 12.13.56](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 12.13.56.png)

- 하나의 AZ에 여러개의 EC2 인스턴스
- 여러명의 게임, Layer4에서 유저들끼리 커뮤니케이트
- 고가용성과 cost-effective로 만들고 싶어함.



layer4 ==> Network Load Balancer

Auto Scailing에서 여러 MultiAZ로 분할하고,  계층4처리를 위한 NLB와의 통합을 통해 고가용성과 비용 효율성이 높은 아키텍처 제공 가능.

The answer is C, E



### 31. 

![스크린샷 2021-10-21 오전 12.20.11](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 12.20.11.png)

- web app (backed bay RDS MySQL DB)
- automated backups run daily not encrypted
- require future backups to be encrypted and unencrypted bakups to be destroyed
- make at least one encrypted backup before destroying old backups
- 무엇이 선행되어야 하는가?

The answer is C.

encrypted db에서만 encrypted backup/snashot을 얻을 수 있다. ==> 그러므로 백업하기 전 맨처음 db를 encrypt 해야한다.

### 

### 32.

![스크린샷 2021-10-21 오전 12.32.51](../Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 12.32.51.png)

- 웹사이트, 다수의 ALB 뒤로
- 컨텐츠에 대해 전세계에서 다른 배포 저작권을 가지고 있다.
- 올바른 content를 서비스 받기, 배급 저작권을 위반 없이



web site hosted behind multiple ALBs

Geolocation routing은 유저들의 지리적 위치에 따라 리소스를 결정한다.

Geolocation routing을 통해 유저의 언어로 표현할 수 있다.

geolocation routing을 사용하면 배급을 제한할수 있다. distribution rights를 가지고 있는 사람에게만 허용할 수 있다.

The answer is C.

==Configure Amazon Route 53 with a geolocation policy.==



### 33.

![스크린샷 2021-10-21 오전 1.02.53](../Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 1.02.53.png)

- 새로운 aws 계정 만듬
- root user access를 보안을 유지 해야한다.



The answer is A, B



### 34.

![스크린샷 2021-10-21 오전 1.44.48](../Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 1.44.48.png)

- E-Commerce
- 로그 데이터 S3에 백업
- 얼마나 빈번하게 로그가 접근될지, 어떤 로그가 가장 많이 억세스 될지 불확실하다.
- 가장 저비용으로 유지하고 싶어함



The answer is B

S3 Intelligent-Tiering is best for storage patterns which are unknown or changing access and is designed for cost optimization.



### 35.

![스크린샷 2021-10-21 오전 1.50.35](../Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 1.50.35.png)

- EC2 instance in an ASG behind an ALB
- CloudFront distribution, AWS WAF to protect aginst SQL injection attacks
- ALB is the origin for the CloudFront distribution
- there's an external malicious IP that needs to be blocked from accessing the website

![스크린샷 2021-10-21 오전 1.58.28](../Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 1.58.28.png)

The answer is  B.

CORRECT: "Modify the configuration of AWS WAF to add an IP match condition to block the malicious IP address" is the correct answer. 

INCORRECT: "Modify the network ACL on the CloudFront distribution to add a deny rule for the malicious IP address" is incorrect as CloudFront does not sit within a subnet so network ACLs do not apply to it.  

INCORRECT: "Modify the network ACL for the EC2 instances in the target groups behind the ALB to deny the malicious IP address" is incorrect as the source IP addresses of the data in the EC2 instances’ subnets will be the ELB IP addresses.  

INCORRECT: "Modify the security groups for the EC2 instances in the target groups behind the ALB to deny the malicious IP address." is incorrect as you cannot create deny rules with security groups.



### 36.

![스크린샷 2021-10-21 오전 2.05.49](../Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 2.05.49.png)

- ​    design two-step order process
- first step : 동기적, 적은 지연
- second step : 분리된 구성요소에서 실행됨.
- 정확하게 이뤄져야 한다. 



The answer is A.

ensure the order of execution ==> SQS FIFO

not C because SNS does not guarantee orderingm, if it were an SNS FIFO topic then that would've been correct, but just SNS topic will not guarantee ordering.



### 37.

![스크린샷 2021-10-21 오전 2.14.58](../Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 2.14.58.png)

- two-tier architecture includes a web layer and database layer
- vulnerable to cross-site scripting(XSS) attacks



The answer is C

To fix cross-site scripting problem ==> AWS WAF

WAF is tightly integrated with Application Load Balancer not CLB



### 38.

![스크린샷 2021-10-21 오전 2.18.22](../Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 2.18.22.png)

- RDS MySQL Multi-AZ DB instance 데이터 스토리지의 이동.
- db instance는 fetch data시에 느려진다.
- read write에 영향을 주어 느린 리스폰스 타임이 된다.\\



The answer is D

Internal system fetch the data == performing only SELECT statement

Read replicas are used for SELECT only kind of statements.

=> Everytime there's a question on Db slowness, you can bet the answer will be "Read Replica", whether the DB is MySQL, Postgre, Aurora, RDS... READ REPLICA





### 39.

### ![스크린샷 2021-10-21 오전 2.23.22](../Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 2.23.22.png)

- EC2 instances across multi-AZ
- ASG behind ALB
- performs best when CPU utilization near 40%
- how to maintain the desired performance across all instances in the group



target tracking ==> 평균 CPU 사용률을 설정할 수 있다. 이후 asg는 이 값을 유지하도록 인스턴스 수를 조정한다.

​							      예를들어 target tracking을 통해 CPU 사용률을 40%로 유지하는 것도 가능하다.





### 40.

![스크린샷 2021-10-21 오전 2.31.28](../Library/Application Support/typora-user-images/스크린샷 2021-10-21 오전 2.31.28.png)

- instances can be scalable
- asg scale up to 20instances during work hours. scale down to 2instances overnight
- very slow when the day begins runs well by mid-morning
- keep cost to a minimum and give solution



A,D cannot be answer cuz it says minimum cost

B,C are both a better options

The problem is that Auto Scaling is not responding fast enough to the increase in demand.

Decreasing the cool down period can make Auto Scaling more responsive but still run less than 20 instances at first. therefore will cost less money.

So C is correct.