### 4. 
<img width="670" alt="스크린샷 2021-10-23 오전 10 48 27" src="https://user-images.githubusercontent.com/45779378/138537894-f09ca0d7-b6ac-45f5-acbc-5fe52fea7f4e.png">

- Serverfarm : 컴퓨터 서버들의 모임, 수천개의 컴퓨터로 이루어짐

  

  B. Window file server farm that uses DFSR ==> Amazon FSx



### 9.
<img width="656" alt="스크린샷 2021-10-23 오전 10 49 15" src="https://user-images.githubusercontent.com/45779378/138537927-3f2ebc68-7a72-42dd-8dba-c6719a7d9d51.png">

- 해당 앱의 DB에 대해 Amazon Aurora Multi-AZ 배포를 하고 있다.
- db read가 높은 입출력을 초래하고 db write를 지연시키게 한다고 한다.
- write요청과 read요청을 분리시키려면 어떻게 해야하는가?



A. Can't enable caching on the aurora database

==B. in aurora, you can actually read from the Multi-AZ stanby instance.==

aurora는 replica를 가지고 있고 이것은 Multi-AZ가 될수있다.

또한 read endpoint로도 쓰일 수 있다.

rds와는 조금 다르다.

C.  Multi-AZ에서는 aurora는 이미 read replica를 가지고 있기 때문에 create할 필요없다.

D. db를 만드는건 불가능.



### 15.
<img width="664" alt="스크린샷 2021-10-23 오전 10 49 59" src="https://user-images.githubusercontent.com/45779378/138537955-0e2b3a85-311e-49f9-be11-1ad303f9ce8b.png">


- 데일리 리포트 정적 HTML pages로써 받고 있음.
- 수백만 뷰가 있을것으로 예상, 전세계에
- S3 버킷에 저장되어있고 효율적인 설계를 해야함.



Static content on S3 ==> CloudFront

==D==



### 18.
<img width="675" alt="스크린샷 2021-10-23 오전 10 50 46" src="https://user-images.githubusercontent.com/45779378/138537991-2eaa1de0-99f7-4689-8764-53e20feb45e1.png">

- Image customization parameters는 API Gateway API로 전송 받음
- 온디맨드 방식에 따라 만들어 질 것이다.
- 링크를 통해 보거나 다운로드 할 수 있다.
- 이미지를 보는 것이 고가용성이여야 한다.
- 가장 비용 효율적인 솔루션은?



cost-effective ==> not EC2 instance with ELB(사용하지 않을 때도 ongoing costs필요)

Lambda ==> only pay when function is running.

lambda는 manipulation 가능 ==> 다른 S3안에 원본과 변경된 이미지 둘다 저장 가능(단 다른 버켓) ==> highly available & scalable

CloudFront ==> easy to send data to User through multiple Edge locations.



The answer is B.



### 19.
<img width="681" alt="스크린샷 2021-10-23 오전 10 51 29" src="https://user-images.githubusercontent.com/45779378/138538018-d7400d9e-d1d5-425e-a23d-f22be55d91d9.png">

- 비즈니스 데이터셋을 S3으로 migrate계획
- a single S3 bucket in the us-east-1 Region에 저장 가능한 버전.
- 재해 복구 정책에 의해 모든 데이터는 여러 region에 있어야 한다. 그러기 위해서 S3을 어떻게 디자인 해야하는가?



Cross region replication(CRR) or Same region replication(SRR) needs S3 versioning to be enabled.

복제를 사용하면 S3버킷간에 개체를 자동-비동기식으로 복사 가능



### 20.
<img width="669" alt="스크린샷 2021-10-23 오전 10 52 04" src="https://user-images.githubusercontent.com/45779378/138538045-316282f0-321a-48a3-86da-1457d007db4e.png">

- VPC에서 EC2 인스턴스가 운영되고 있음
- 객체를 저장하고 읽기 위해 S3 API를 호출해야한다. 
- 어플 내의 모든 인터넷에 연결된 트래픽을 규제해야한다.



B. Gateway endpoint(인터넷을 사용하기 위해서는 모두가 지나가야 하기 때문, 그러므로 해당 항목을 설정한다면 모든 인터넷에 연결된 트래픽을 규제할 수 있게 된다.)



### 22.
<img width="676" alt="스크린샷 2021-10-23 오전 10 52 53" src="https://user-images.githubusercontent.com/45779378/138538070-21dc279b-971b-4693-9e4c-67aa7b7dab70.png">

- HPC(High Performance Computing) App을 온프레미스(자체 서버)에서 AWS Cloud로 Migrate
- uses tiered storage on premises 고수행 패러렐 용량 
- 더 경제적인 콜드 스토리지 ==> 실행되지 않을때도 hold
- 주기적으로 실행하는 동안 애플리케이션을 지원



A. Amazon S3 for cold data storage

D. Amazon FSx for Lustre for high-performance parallel storage.



Amazon FSx for Lustre는 빠른 워크로드들의 프로세싱(머신러닝, 비디오 프로세싱, 파이낸셜 모델링, EDA)에 최적화된 high-performance 파일 시스템을 제공한다.

또한 이러한 워크로드들은 신속한 확장가능한 파일시스템을 필요로 하며, S3처럼 오랜기간 데이터를 저장한다.



### 23.
<img width="683" alt="스크린샷 2021-10-23 오전 10 53 31" src="https://user-images.githubusercontent.com/45779378/138538079-a908e8c2-1df4-44b9-8c93-1cc587be02c1.png">

- EC2 instances in a single region

- need to ensure that the resources can also be deployed to a second Region.

  

B, D ==> AMI는 지역적이여서 도착리전으로 복사되어야 한다. 한번 복사되면 새로운 인스턴스는 새로운 리전에서 실행되어야 한다.



### 24.
<img width="656" alt="스크린샷 2021-10-23 오전 10 54 25" src="https://user-images.githubusercontent.com/45779378/138538100-e41018c5-040d-40bd-b92c-5eadd471e009.png">

- ensure API calls to EC2 instace ==> DynamoDB in a VPC
- do not traverse the internet



B.Create a gateway endpoint for DynamoDB.

A.Create a route table entry for the endpoint.

Amazon DynamoDB & Amazon S3는 gateway endpoint를 지원한다. 

gateway endpoint를 가지고, VPC의 엔드포인트를 만들수있다. 엑세스 허용 정책을 만들수도 있다.

그리고 루트테이블 엔트리를 들어가게 하기위해 루트테이블을 명시한다.



### 25.
<img width="662" alt="스크린샷 2021-10-23 오전 10 55 04" src="https://user-images.githubusercontent.com/45779378/138538122-80fa4948-5d45-40a5-8569-70afe2408f6c.png">

- 레거시 어플리케이션 ==> 싱글 인스턴스 RDS MySQL에 의존중(암호화되어있지 않은 데이터베이스)
- 새로운 준수 필요에 따라 모든 존재하는, 새로운 데이터들은 암호화가 되어야 한다.
- 어떻게 구현할것인가?



RDS인스턴스의 스냅샷 ==> 스냅샷의 암호화된 복제 ==> 암호화된 스냅샷으로부터 RDS인스턴스를 복구함.



### 26.
<img width="672" alt="스크린샷 2021-10-23 오전 10 55 38" src="https://user-images.githubusercontent.com/45779378/138538135-577364a0-d092-4202-a6f0-2e92b8074f6b.png">

- 예측가능한 유지보수를 수행.
- 수천개의 IoT센서들 실행, 실시간으로 aws에 데이터를 보냄
- 순서대로 처리하고, 데이터가 추가적인 프로세싱에서도 안전해야함



A. Use Amazon Kinesis Data Streams for real-time events with a partition for each equipment asset. Use Amazon Kinesis Data Firehose to save data to Amazon S3.

Kinesis Data Streams, 	Kinesis Data Firehose,	Amazon S3

ordered manner ==> SQS standard queue not ordered

SQS FIFO ==> not effective for large amounts of realtimedata

Kinesis Data Streams + Kinesis DataFirehose is way effective.

And EBS is not a target of Firehose. 

Kinesis Firehose's target is S3.

Kinesis Data Stream enables big data's real-time processing.



### 27.
<img width="668" alt="스크린샷 2021-10-23 오전 10 56 14" src="https://user-images.githubusercontent.com/45779378/138538154-c2e0981e-1612-445d-b82e-829e956165f7.png">

- EC2인스턴스들이 웹사이트를 운영, behind an ALB==>scalable
- mix of dynamic and static content.
- User around the globe said the website is slow
- 어떤 방법이 웹사이트의 퍼포먼스를 발전시킬것인가.



A. Create an Amazon CloudFront distribution and configure the ALB as an origin. Then update the Amazon Route 53 record to point to the CloudFront distribution.

CloudFront는 low latency access를 제공한다 to both static and dynamic content for global users.

그리고 Route53과 통합될수 있다..
