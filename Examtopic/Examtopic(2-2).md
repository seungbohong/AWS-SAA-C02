### 81.

![스크린샷 2021-10-27 오전 1.12.23](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 1.12.23.png)

- S3 bucket
- with SQS queue
- receive events when new objects are created
- must remain intact

![스크린샷 2021-10-27 오전 1.28.15](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 1.28.15.png)



The answer is D.

SNS는 SQS와 긴밀하게 움직인다.

SNS을 사용시 애플리케이션이  "push" 매커니즘을 통해 알람을 여러 구독자들 한테 보낼 수 있으므로 업데이트를 주기적으로 확인하거나 "poll" 필요 없음. SNS과 SQS를 함께 사용하면 즉각적인 이벤트 알림을 필요로 하는 애플리케이션에 메세지를 전송할 수 있다.

C가 아닌 이유 : sns 사용시 poll을 할 필요가 없다. 



### 82.

![스크린샷 2021-10-27 오전 1.32.31](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 1.32.31.png)

- EC2 instances in private subnets
- needs to access DynamoDB table
- secure way while the traffic does not leave the AWS network



A is correct.

Why A?

1. application runs on Amazon EC2 instances in private subnets
2. secure way to access the DynamoDB table while ensuring that the traffic does not leave the AWS network



VPC endpoint for making sure it does not leave AWS network.



### 83.

![스크린샷 2021-10-27 오전 1.35.48](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 1.35.48.png)

- fears the database may not handle the new load the following month because  the single RDS for MySQL instance has triggered alarms related to resource exhaustion due to read requests.



A is correct. ==> typical use case for read replicas



### 84.

![스크린샷 2021-10-27 오전 1.39.23](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 1.39.23.png)

- store video archives in AWS
- cost-effective, rarely need to restore
- file must be available in a maximum of five minutes



The answer is A.

Expedited retrievals enables you to access data in 1-5minutes.

S3 Glacier is the cheapest option



### 85.

![스크린샷 2021-10-27 오전 1.43.15](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 1.43.15.png)

- VPC with multi private subnets in multi-AZ and one public subnet in one of the multi-AZ
- public subnet ==> launch a NAT gateway
- backup plan ready
- highly-available



The answer is C.

NAT gateways are highly available than instances ==> not B&D

A looks good but C provide more HA than A



### 86.

![스크린샷 2021-10-27 오전 1.48.14](/Users/hongseungbo/Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 1.48.14.png)

- multiple copies be stored in different locations
- each record must be stored for 7years
- SLA to provide records to gov agencies for the first 30 days and then within 4hours of a request thereafter



A is correct.

stored in different locations --> cross-region replication

after 30days ==> Glacier using lifecycle policy



==TIP== : If retrieval time is 12hours or more(not 4hours), then answer would be Deep archieve.



### 87.

### ![스크린샷 2021-10-27 오전 1.53.17](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 1.53.17.png)

- centralize
- EC2 instances with ensuring all instances provisioned through EC2 ASG successfully send reports to the system as soon as they are launched
- most efficient way



The answer is B

Lifecycle hooks allow you to control what happens when your EC2 instances are launched and terminated as you scale out and in.



### 88. 

![스크린샷 2021-10-27 오전 1.58.34](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 1.58.34.png)

- hybrid cloud connectivity using AWS Direct Connect
- migrating data to S3
- fully managed solution that will automate and accelerate the replication of data between the on-premises storage systems and AWS storage services.
- keep the data private



Ans is A 

DataSync is for actual data transfer on-premises to AWS whereas Storage Gateway is to retain access to the data that is transferred to AWS.

==Private Data migration ==> DataSync + endpoint==



### 89.

![스크린샷 2021-10-27 오전 2.03.17](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 2.03.17.png)

- 150TB data stored in on-premises ==> AWS Cloud within the next month
- network connection allows up to 100Mbps during the night only
- cost-effective and meet the migration deadline



The answer is B.

couple of AWS Snowball devices(80TB of each) should able to move 150TB easily.



### 90.

![스크린샷 2021-10-27 오전 2.06.33](../../../../Library/Application Support/typora-user-images/스크린샷 2021-10-27 오전 2.06.33.png)

- EC2 instance in a private subnet
- a large number of queries 
- performance degrading due to an increase in complex queries
- any recommends?



The answers are B&E

a large number of queries involve multiple table joins ==> RDS

improve performance ==> Read replica