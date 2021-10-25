### 71.

![스크린샷 2021-10-26 오전 1.27.35](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-26 오전 1.27.35.png)

- videos real time
- available on demand
- global online audience



The answer is A.

You can use CloudFront to deliver video on demand (VOD) or live streaming video or live streaming video using any HTTP origin.





### 72.

![스크린샷 2021-10-26 오전 1.39.27](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-26 오전 1.39.27.png)

- 3 tier image sharing app
- EC2 instance for the front-end layer, another for back-end tier, and a third for the MySQL database.
- highly available, requires least amount of changes to the application



The answer is D.

highly available ==> "Multi AZ"

 requires the least amount of changes to the application. ==> "Elastic Beanstalk automatically"



### 73.

![스크린샷 2021-10-26 오전 1.38.57](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-26 오전 1.38.57.png)

- 4hours every night
- time to complete jobs is expected to remain constant
- cannot be interrupted once started
- once completed system is expected to run for a minimum of 1 year.



The answer is D.

A ==> X : 스팟인스턴스에서는 워크로드는 제거될 수도 있으므로 인터럽트 받을 수도 있다.

B ==> X : 온디맨드 인스턴스는 비용효율적이지는 않다.

C==> Scheduled Reserved Instances보다는 비싸지만 현재로써는 C가 맞다.

D==> (옛날기준 정답)O : Scheduled Reserved Instances라면 정해진 시간에 비용을 줄여서 사용 가능하다.(현재에는 이용불가이다.)



### 74.

![스크린샷 2021-10-26 오전 1.46.36](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-26 오전 1.46.36.png)

- 유저 데이터를 캡쳐해서 저장한다.
- static이다 EC2
- front-end sends to the backend app running on separate EC2 instance
- backend app stores the data in RDS
- 분리를 하고 확장가능하게 할 수 있는가?



==static frontend ==> S3==

==decouple ==> SQS==



D is the answer.



### 75.

![스크린샷 2021-10-26 오전 1.52.54](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-26 오전 1.52.54.png)

- managed storage solution
- HPC
- AWS Fargate
- concurrent access to files and deliver high performance



Ths answer is B.

HPC ==> FSx



HPC ==> FSx for Lustre, but isn't supported by Fargate for now. but "establish an IAM role" allows Fargate to communicate with FSx for Lustre.



### 76.

![스크린샷 2021-10-26 오전 1.56.51](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-26 오전 1.56.51.png)

- multi-tier architecture
- most viable multi-tier option
- must be accessible from the REST API



The answer is A.

accessible from REST API and store the data.

Athena with S3 can store and retrieve the data and also can access from REST API.



### 77.

![스크린샷 2021-10-26 오전 2.04.32](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-26 오전 2.04.32.png)

- scalable
- resilient against malicious internet activity and attacks



the answer is B.

protect against malicious IP ==> AWS WAF



### 78.

### ![스크린샷 2021-10-26 오전 2.06.26](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-26 오전 2.06.26.png)

- AWS Lambda Functions
- DB credentials remove from the source code
- credentials must be stored and rotated on an ongoing basis to meet security policy requirements



store credential database & associate the Lamda function with a role that can retrieve the pwd from Secrets Manager given ==> AWS Secrets Manager



### 79.

![스크린샷 2021-10-26 오전 2.10.59](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-26 오전 2.10.59.png)

- on-premise
- keep records indefinitely
- disable any modifications once they stored
- access at all levels
- there are millions of records not being used
- current infra is running out of space



The answer is A.

move existing data ==> AWS DataSync

granular audit access ==> CloudTrail S3 Data events



### 80. 

### ![스크린샷 2021-10-26 오전 2.18.50](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-26 오전 2.18.50.png)

- S3 secondary copy (on-premises dataset)
- rarely need to access this copy
- cost-effective



D is correct.

S3 One Zone-Infrequent Access(S3 One Zone-IA)

 

S3 One Zone-IA는 자주 엑세스 하지 않는 데이터의 사례에 적당하다.

secondary copy ==> One Zone-IA

