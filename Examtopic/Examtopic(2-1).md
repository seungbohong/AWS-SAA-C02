### 71.
<img width="794" alt="스크린샷 2021-10-26 오전 2 24 26" src="https://user-images.githubusercontent.com/45779378/138741711-7d496dd4-103c-4d05-bd7a-7184cad8f187.png">

- videos real time
- available on demand
- global online audience



The answer is A.

You can use CloudFront to deliver video on demand (VOD) or live streaming video or live streaming video using any HTTP origin.





### 72.
<img width="762" alt="스크린샷 2021-10-26 오전 2 24 51" src="https://user-images.githubusercontent.com/45779378/138741763-9efe3fb7-61ce-4a4f-8934-7522168bb897.png">

- 3 tier image sharing app
- EC2 instance for the front-end layer, another for back-end tier, and a third for the MySQL database.
- highly available, requires least amount of changes to the application



The answer is D.

highly available ==> "Multi AZ"

 requires the least amount of changes to the application. ==> "Elastic Beanstalk automatically"



### 73.
<img width="782" alt="스크린샷 2021-10-26 오전 2 25 07" src="https://user-images.githubusercontent.com/45779378/138741805-68c6b83c-31da-4943-8fcd-e869ebc358f6.png">

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
<img width="772" alt="스크린샷 2021-10-26 오전 2 25 30" src="https://user-images.githubusercontent.com/45779378/138741853-a0910d13-3a18-400f-8da9-66fbe7f2d665.png">

- 유저 데이터를 캡쳐해서 저장한다.
- static이다 EC2
- front-end sends to the backend app running on separate EC2 instance
- backend app stores the data in RDS
- 분리를 하고 확장가능하게 할 수 있는가?



==static frontend ==> S3==

==decouple ==> SQS==



D is the answer.



### 75.
<img width="786" alt="스크린샷 2021-10-26 오전 2 25 44" src="https://user-images.githubusercontent.com/45779378/138741894-b79d10a3-7083-4ac7-ad05-6d40e92b6b29.png">

- managed storage solution
- HPC
- AWS Fargate
- concurrent access to files and deliver high performance



Ths answer is B.

HPC ==> FSx



HPC ==> FSx for Lustre, but isn't supported by Fargate for now. but "establish an IAM role" allows Fargate to communicate with FSx for Lustre.



### 76.
<img width="789" alt="스크린샷 2021-10-26 오전 2 25 57" src="https://user-images.githubusercontent.com/45779378/138741923-7d8c29aa-8d3f-4093-84f6-6ac9cad1a3ac.png">

- multi-tier architecture
- most viable multi-tier option
- must be accessible from the REST API



The answer is A.

accessible from REST API and store the data.

Athena with S3 can store and retrieve the data and also can access from REST API.



### 77.
<img width="781" alt="스크린샷 2021-10-26 오전 2 26 09" src="https://user-images.githubusercontent.com/45779378/138741945-db750bb9-9630-4808-a556-6f5c76ae0219.png">

- scalable
- resilient against malicious internet activity and attacks



the answer is B.

protect against malicious IP ==> AWS WAF



### 78.
<img width="783" alt="스크린샷 2021-10-26 오전 2 26 23" src="https://user-images.githubusercontent.com/45779378/138741975-5c5371f4-89ba-4727-b477-501d8a5ec33d.png">

- AWS Lambda Functions
- DB credentials remove from the source code
- credentials must be stored and rotated on an ongoing basis to meet security policy requirements



store credential database & associate the Lamda function with a role that can retrieve the pwd from Secrets Manager given ==> AWS Secrets Manager



### 79.
<img width="776" alt="스크린샷 2021-10-26 오전 2 26 34" src="https://user-images.githubusercontent.com/45779378/138742007-46c55178-5516-49aa-8e88-7322e71e7d4f.png">

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
<img width="769" alt="스크린샷 2021-10-26 오전 2 26 45" src="https://user-images.githubusercontent.com/45779378/138742029-26275440-55be-41ea-8390-16a4d7e65a28.png">

- S3 secondary copy (on-premises dataset)
- rarely need to access this copy
- cost-effective



D is correct.

S3 One Zone-Infrequent Access(S3 One Zone-IA)

 

S3 One Zone-IA는 자주 엑세스 하지 않는 데이터의 사례에 적당하다.

secondary copy ==> One Zone-IA

