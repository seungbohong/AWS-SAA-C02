### 61.

![스크린샷 2021-10-23 오전 1.33.40](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 1.33.40.png)

- 멀티티어 app
- 6개의 EC2, ASG, single AZ, ALB
- highly available.



B is correct



### 62.

![스크린샷 2021-10-23 오전 1.36.59](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 1.36.59.png)

- Linux EC2 instances
- API calls
- all log files must be retained indefinitely
- be analyzed by a reporting tool that must access all file concurrently



D is correct

EFS would have higher performance but it costs more

1) all log files must be retained indefinitely(무기한)
2) will be analyzed by a reporting tool



### 63.

![스크린샷 2021-10-23 오전 1.41.06](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 1.41.06.png)

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

![스크린샷 2021-10-23 오전 1.48.57](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 1.48.57.png)

- 여러 EC2 인스턴스들, ALB, ASG
- custom DNS name and communicates with HTTPs
- SSL certificate
- equal performance globally



The answer is A

CloudFront can help provide the best experience for global users.

and also integrates seamlessly with ALB and provides and option to use custom DNS and SSL certs.



### 65.

![스크린샷 2021-10-23 오전 1.52.06](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 1.52.06.png)

- cloud architecture
- should run in parallel while adding and removing app nodes as needed
- stateless
- ensure that the app is loosely coupled and the job items are durably stored



C is correct

loosely coupled and durably solution ==> SQS(대기중인 작업 수에 따라 동적확장 사용가능)

SQS queue의 항목수를 기반으로 하는 target scaling policy를 사용하면 요구에 따라 애플리케이션 노드를 확장하는데 도움이 된다.



### 66.

![스크린샷 2021-10-23 오전 2.00.27](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 2.00.27.png)

- CSV file stored in an S3 bucket for stastical analysis
- EC2 instance needs permission to efficiently process the CSV data stored in S3 bucket
- Which action is Most secure?



The answer is C.

Identify and Access Management(IAM) enables to manage access to AWS services and resources securely. Configure IAM role with least privilege permissons to the EC2 instance profiile is the most secure way.



### 67.

![스크린샷 2021-10-23 오전 2.06.05](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 2.06.05.png)

- 온프레미스 서버, RDS
- read traffic in different locations
- migrate to aws with the least amount of effort
- DB should support disaster recovery and not affect the company's current traffic flow



The answer is A

read replica can support multi-region



### 68.

![스크린샷 2021-10-23 오전 2.09.35](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 2.09.35.png)

- EC2 instances with ASG behind ELB
- spike traffic(트래픽 급증)
- ensure that the ASG 
- minimize any performance



B is correct.

scale up the ASG before peak time.

anticipating ==>scheduled action.



### 69.

![스크린샷 2021-10-23 오전 2.15.25](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 2.15.25.png)

- multiple EC2 instances
- processes messages from an SQS queue
- writes RDS table
- deletes the message from the queue
- duplicate records are found in the RDS table
- SQS queue doesn't have duplicate messages



Key thing to note:  Your application processing time is more than the visibility timeout. So, increaseing message visibility timeout can help to prevent duplicate entries in RDS.



### 70.

![스크린샷 2021-10-23 오전 2.27.30](../../../Library/Application Support/typora-user-images/스크린샷 2021-10-23 오전 2.27.30.png)

- deny ==> us-east-1과 일치하지 않는 지역은있는 ec2에 액션 불가 --------> us-east-1과 일치하면 액션 가능
- 10.100.100.0/24의 IP주소를 가지고 있는 인스턴스 제거가능



C is correct.

