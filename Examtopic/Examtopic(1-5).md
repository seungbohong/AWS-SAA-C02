### 61.
<img width="674" alt="스크린샷 2021-10-23 오후 4 56 35" src="https://user-images.githubusercontent.com/45779378/138547968-7743616e-9f9c-457e-9847-09d6787bc1ca.png">


- 멀티티어 app
- 6개의 EC2, ASG, single AZ, ALB
- highly available.



B is correct



### 62.
<img width="660" alt="스크린샷 2021-10-23 오후 4 56 51" src="https://user-images.githubusercontent.com/45779378/138547984-39e460bc-ed35-46b8-9c7c-60d38bfdc8e6.png">

- Linux EC2 instances
- API calls
- all log files must be retained indefinitely
- be analyzed by a reporting tool that must access all file concurrently



D is correct

EFS would have higher performance but it costs more

1) all log files must be retained indefinitely(무기한)
2) will be analyzed by a reporting tool



### 63.
<img width="666" alt="스크린샷 2021-10-23 오후 4 57 08" src="https://user-images.githubusercontent.com/45779378/138547997-fd10536d-6531-450b-8e74-68550e773461.png">

- 스트리밍, 실시간 데이터
- stores it in a disk-optimized db system
- in-memory db 
- faster and provides high-availability using data replication



C is correct

Redis는 여러개의 레플리카를 생성한다.

이것은 db reads양 따라 확장되고 highly available cluster를 갖게 해줄것이다.



**ElastiCache is an in-memory database**.

With ElastiCache Memcached : there is no data replication or high availability.

**With ElastiCache Redis : there is read replicas to scale reads and high availability**



### 64.
<img width="662" alt="스크린샷 2021-10-23 오후 4 57 21" src="https://user-images.githubusercontent.com/45779378/138548016-2739d2e4-3dc3-4377-8bea-5a65f886601e.png">

- 여러 EC2 인스턴스들, ALB, ASG
- custom DNS name and communicates with HTTPs
- SSL certificate
- equal performance globally



The answer is A

CloudFront can help provide the best experience for global users.

and also integrates seamlessly with ALB and provides and option to use custom DNS and SSL certs.



### 65.
<img width="911" alt="스크린샷 2021-10-23 오후 4 57 54" src="https://user-images.githubusercontent.com/45779378/138548038-d8312268-aaff-44c8-a6bc-9f19d354f222.png">

- cloud architecture
- should run in parallel while adding and removing app nodes as needed
- stateless
- ensure that the app is loosely coupled and the job items are durably stored



C is correct

loosely coupled and durably solution ==> SQS(대기중인 작업 수에 따라 동적확장 사용가능)

SQS queue의 항목수를 기반으로 하는 target scaling policy를 사용하면 요구에 따라 애플리케이션 노드를 확장하는데 도움이 된다.



### 66.
<img width="657" alt="스크린샷 2021-10-23 오후 4 58 11" src="https://user-images.githubusercontent.com/45779378/138548053-ded58df0-0db9-4380-bd00-7be0a6e15379.png">

- CSV file stored in an S3 bucket for stastical analysis
- EC2 instance needs permission to efficiently process the CSV data stored in S3 bucket
- Which action is Most secure?



The answer is C.

Identify and Access Management(IAM) enables to manage access to AWS services and resources securely. Configure IAM role with least privilege permissons to the EC2 instance profiile is the most secure way.



### 67.
<img width="682" alt="스크린샷 2021-10-23 오후 4 58 24" src="https://user-images.githubusercontent.com/45779378/138548067-57eee884-c1c8-49ef-84df-9deb17341715.png">

- 온프레미스 서버, RDS
- read traffic in different locations
- migrate to aws with the least amount of effort
- DB should support disaster recovery and not affect the company's current traffic flow



The answer is A

read replica can support multi-region



### 68.
<img width="678" alt="스크린샷 2021-10-23 오후 4 58 38" src="https://user-images.githubusercontent.com/45779378/138548081-7f24d34d-ff86-4550-9873-abbc7fd1fdad.png">

- EC2 instances with ASG behind ELB
- spike traffic(트래픽 급증)
- ensure that the ASG 
- minimize any performance



B is correct.

scale up the ASG before peak time.

anticipating ==>scheduled action.



### 69.
<img width="683" alt="스크린샷 2021-10-23 오후 4 58 56" src="https://user-images.githubusercontent.com/45779378/138548095-a1f6e0f3-fdf1-4877-927f-023d2c9e3de4.png">

- multiple EC2 instances
- processes messages from an SQS queue
- writes RDS table
- deletes the message from the queue
- duplicate records are found in the RDS table
- SQS queue doesn't have duplicate messages



Key thing to note:  Your application processing time is more than the visibility timeout. So, increaseing message visibility timeout can help to prevent duplicate entries in RDS.



### 70.
<img width="672" alt="스크린샷 2021-10-23 오후 4 59 19" src="https://user-images.githubusercontent.com/45779378/138548116-cfccaf76-bcea-4da0-8094-8e4c8ab8115a.png">
<img width="677" alt="스크린샷 2021-10-23 오후 4 59 28" src="https://user-images.githubusercontent.com/45779378/138548119-1db87c10-e8c5-4253-b820-4986ed4aa44e.png">

- deny ==> us-east-1과 일치하지 않는 지역은있는 ec2에 액션 불가 --------> us-east-1과 일치하면 액션 가능
- 10.100.100.0/24의 IP주소를 가지고 있는 인스턴스 제거가능



C is correct.

