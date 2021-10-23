### 41. 

![스크린샷 2021-10-22 오후 7.48.37](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 7.48.37.png)

- 미국과 유렵에서 서비스를 제공
- DB tier, Web server tier
- DB tier ==> MySQL hosted in us-east-1
- Amazon Route 53 geoproximity routing (closest region)
- European is a bit more slow than US



The answer is D.

DB slow ==> configure read replicas in one of a Europe Regions



### 42.

![스크린샷 2021-10-22 오후 7.52.31](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 7.52.31.png)

- static website on-premises(company's server)
- migrate to AWS
- 전세계 모두 빠르게 로드 하도록
- 또한 비용효율적인 솔루션



static website & load quickly all over the world

the most cost-effective option is to migrate the website to an Amazon S3 bucket and configure that bucket for static website hosting.

And to enable good performance for global users, SA should configure a CloudFront distribution with the S3 bucket as the origin. 

This will cache the static content around the world closer to users.



### 43.

![스크린샷 2021-10-22 오후 7.57.36](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 7.57.36.png)

- Design HPC based on Amazon Linux
- workload stores and processes a large amount of things



HPC + Linux ==> FSx for Lustre

Lustre actually stands for Linux and cluster ==> hence it's perfect HPC



### 44.

![스크린샷 2021-10-22 오후 7.59.36](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 7.59.36.png)

- public-facing website running on EC2 instance as a Microsoft Active Directory domain controller
- recommend a new design would improve security and minimize Admin demand



The answer is A.

reduce risk = remove Active Directory from that EC2

Minimize admin = use AWS Directory Service



### 45.

![스크린샷 2021-10-22 오후 8.03.16](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 8.03.16.png)

- static website within an S3 bucket
- ensure that data can be recovered in case of accidential deletion.



Accidential deletion ==> Amazon S3 versioning

S3 Versioning provides the ability to recover from both unintended user actions and application failures.



### 46.

![스크린샷 2021-10-22 오후 8.05.50](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 8.05.50.png)

- OLTP(온라인 거래 프로세싱) on RDS MySQL DB instance
- new reporting tool that will access the same data.
- highly-available and not impact the performance of application



The answer is B

Why not C? : RDS is a managed service and AWS handles the scaling part.



### 47.

![스크린샷 2021-10-22 오후 8.09.46](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 8.09.46.png)

- a small data with no virtualized compute resources
- stored on an NFS volume
- daily offsite backup of the NFS volume



The answer is  **B**

small data closet with no virtualized compute resources ==  ==the need for onsite hardware appliance==



오프사이트 백업은 원격 서버나 오프사이트로 전송되는 미디어에 데이터를 백업하는 방법이다.

1. 가장 일반적인 오프사이트 백업의 두 가지 형태는 **클라우드 백업**과 **테이프 백업**이다.



### 48.

![스크린샷 2021-10-22 오후 8.15.28](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 8.15.28.png)

- multiple EC2 instances 

- storing data on EBS volumes

- increase the resiliency(탄력) in case of a failure and provide storate complies with

  atomicity, consistency, isolation and durability(ACID)

ACID storage ==> EFS



### 49.

![스크린샷 2021-10-22 오후 8.18.34](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 8.18.34.png)

- limit access to specific services or actions
- accounts belong to a large org in AWS Organizations.
- must be scalable, a single point where permissions can be maintained



The answer is D

SCPs(Service Control Policies) 

**Scalable, Centralised, a single point** ==> SCP(Service Control Policy)



### 50.

![스크린샷 2021-10-22 오후 8.23.53](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-22 오후 8.23.53.png)

- 매일밤 로그 프로세싱을 필요로함
- 로그의 숫자와 사이즈는 알려지지 않고 24시간만 운영할 계획이다.
- the most cost-effective



The answer is B

The size and number of logs is unknown ==> 



=> Intelligent Tier에 파일을 직접 보낼 수 있으므로 Intelligent Tier 될 수 있습니다. 그러나 "최소 청구 가능액"은 30일간, 즉 파일을 24시간 보관하더라도 30일간 청구하는 것을 기억합니다. S3 Standard에는 최소청구가능이 없으며 사용일(24시간)만 부과됩니다.

= > 로그의 사이즈와 수가 불명확하여, 24시간만 보관 됩니다. 이것은 소스입니다. 로그는 24시간 후에 자동적으로 로테이션 됩니다. 목적지에서 그들은 시간을 지정하지 않았다. IA는 기본 30일입니다. 사이즈는 128KB입니다.이 두 개는 모르겠어요. S3로 하겠습니다

= > S3Standard-IA 및 S3One Zone-IA 스토리지 클래스는 최소 30일간 저장할 예정인 128KB 이상의 오브젝트에 적합합니다. 30일간의 최소 저장기간이 종료되기 전 오브젝트 삭제 시 30일간 과금됩니다.

=> S3 Intelligent-Tiering, S3 Standard-IA 및 S3 One Zone-IA 스토리지는 최소 30일간의 스토리지 기간 동안 충전됩니다.

=>그리고 S3 Glacier와 S3 Glacier 딥 아카이브에 아카이브 된 오브젝트는 각각 최소 90일과 180일의 보존 기간이 있습니다. 90일 전과 180일 전에 삭제된 오브젝트는 남은 일수의 보관료와 동일한 비율의 요금이 발생합니다.

=> A: Glacier는 싸지만, 최소 90일의 보존기간이 있습니다.즉, 24시간 이내에 데이터를 삭제해도 결국 90일 분의 지불이 됩니다. 그 때문에, 실제로는 s3 표준 B보다 코스트가 듭니다. 하지만 이런 상황에서 비용 효율이 가장 높은 C: 스토리지 클래스는 전혀 없습니다. 계층화된 첫 번째 데이터를 사용하려면 S3D여야 합니다.처음에는 싸 보이지만 IA와 One Zone-IA에는 최소 30건의 스토리지 요금이 듭니다.24시간 이내에 삭제된 데이터입니다만, 30일간 지불해 주시기 바랍니다. 그러니까 실제로는 S3 표준보다 높죠.

