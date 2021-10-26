### 81.
<img width="764" alt="스크린샷 2021-10-27 오전 2 10 51" src="https://user-images.githubusercontent.com/45779378/138927691-709ebf98-28bb-4b9f-8e40-bc3790c6ecb0.png">

- S3 bucket
- with SQS queue
- receive events when new objects are created
- must remain intact
- 
<img width="827" alt="스크린샷 2021-10-27 오전 2 11 02" src="https://user-images.githubusercontent.com/45779378/138927721-24cfb16f-7bf2-4b0c-be64-aa2bafd92a46.png">

The answer is D.

SNS는 SQS와 긴밀하게 움직인다.

SNS을 사용시 애플리케이션이  "push" 매커니즘을 통해 알람을 여러 구독자들 한테 보낼 수 있으므로 업데이트를 주기적으로 확인하거나 "poll" 필요 없음. SNS과 SQS를 함께 사용하면 즉각적인 이벤트 알림을 필요로 하는 애플리케이션에 메세지를 전송할 수 있다.

C가 아닌 이유 : sns 사용시 poll을 할 필요가 없다. 



### 82.
<img width="795" alt="스크린샷 2021-10-27 오전 2 11 18" src="https://user-images.githubusercontent.com/45779378/138927765-acd3e1c4-c559-41ed-bbe5-2c3b795b1201.png">

- EC2 instances in private subnets
- needs to access DynamoDB table
- secure way while the traffic does not leave the AWS network



A is correct.

Why A?

1. application runs on Amazon EC2 instances in private subnets
2. secure way to access the DynamoDB table while ensuring that the traffic does not leave the AWS network



VPC endpoint for making sure it does not leave AWS network.



### 83.
<img width="786" alt="스크린샷 2021-10-27 오전 2 14 01" src="https://user-images.githubusercontent.com/45779378/138928175-c7a21de5-878b-4da4-b4bb-95f99ca7a9c7.png">

- fears the database may not handle the new load the following month because  the single RDS for MySQL instance has triggered alarms related to resource exhaustion due to read requests.



A is correct. ==> typical use case for read replicas



### 84.
<img width="789" alt="스크린샷 2021-10-27 오전 2 11 38" src="https://user-images.githubusercontent.com/45779378/138927809-daa02c71-3633-428b-a345-13d8be2aa244.png">

- store video archives in AWS
- cost-effective, rarely need to restore
- file must be available in a maximum of five minutes



The answer is A.

Expedited retrievals enables you to access data in 1-5minutes.

S3 Glacier is the cheapest option



### 85.
<img width="788" alt="스크린샷 2021-10-27 오전 2 12 06" src="https://user-images.githubusercontent.com/45779378/138927875-180e1848-9bda-40e8-9327-25f9954bcd09.png">

- VPC with multi private subnets in multi-AZ and one public subnet in one of the multi-AZ
- public subnet ==> launch a NAT gateway
- backup plan ready
- highly-available



The answer is C.

NAT gateways are highly available than instances ==> not B&D

A looks good but C provide more HA than A



### 86.
<img width="786" alt="스크린샷 2021-10-27 오전 2 12 16" src="https://user-images.githubusercontent.com/45779378/138927905-9c763acb-290c-49d8-84b5-6d453877685c.png">

- multiple copies be stored in different locations
- each record must be stored for 7years
- SLA to provide records to gov agencies for the first 30 days and then within 4hours of a request thereafter



A is correct.

stored in different locations --> cross-region replication

after 30days ==> Glacier using lifecycle policy



==TIP== : If retrieval time is 12hours or more(not 4hours), then answer would be Deep archieve.



### 87.
<img width="782" alt="스크린샷 2021-10-27 오전 2 12 23" src="https://user-images.githubusercontent.com/45779378/138927919-4c6eeaea-de5d-4af5-9101-c4886c0e59f7.png">

- centralize
- EC2 instances with ensuring all instances provisioned through EC2 ASG successfully send reports to the system as soon as they are launched
- most efficient way



The answer is B

Lifecycle hooks allow you to control what happens when your EC2 instances are launched and terminated as you scale out and in.



### 88. 
<img width="789" alt="스크린샷 2021-10-27 오전 2 12 32" src="https://user-images.githubusercontent.com/45779378/138927936-c21e5341-be30-4e0c-a397-9667438cfe6b.png">

- hybrid cloud connectivity using AWS Direct Connect
- migrating data to S3
- fully managed solution that will automate and accelerate the replication of data between the on-premises storage systems and AWS storage services.
- keep the data private



Ans is A 

DataSync is for actual data transfer on-premises to AWS whereas Storage Gateway is to retain access to the data that is transferred to AWS.

==Private Data migration ==> DataSync + endpoint==



### 89.
<img width="786" alt="스크린샷 2021-10-27 오전 2 12 38" src="https://user-images.githubusercontent.com/45779378/138927944-da97dc86-e342-4bda-81d9-e080006f56c8.png">

- 150TB data stored in on-premises ==> AWS Cloud within the next month
- network connection allows up to 100Mbps during the night only
- cost-effective and meet the migration deadline



The answer is B.

couple of AWS Snowball devices(80TB of each) should able to move 150TB easily.



### 90.
<img width="771" alt="스크린샷 2021-10-27 오전 2 12 44" src="https://user-images.githubusercontent.com/45779378/138927966-563a0740-44e0-4cbe-b536-9679f85478e2.png">

- EC2 instance in a private subnet
- a large number of queries 
- performance degrading due to an increase in complex queries
- any recommends?



The answers are B&E

a large number of queries involve multiple table joins ==> RDS

improve performance ==> Read replica
