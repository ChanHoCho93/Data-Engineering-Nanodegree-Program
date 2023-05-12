#### NoSQL Data Models

>Learning Objective
>
>* Basics of NoSQL database design
>* Denormalization
>* Primary keys
>* Clustering columns
>* The WHERE clause



>When to use NoSQL
>
>* 데이터의 고가용성 필요 : 시스템이 항상 가동되고 중단 시간이 없음
>* 많은 양의 데이터 보유
>* 선형 확장성 필요 : 성능이 선형적으로 증가하도록 시스템에 더 많은 노드를 추가해야 함
>* Low Latency : 전송 명령을 수신한 후 데이터를 전송하기까지의 지연 시간이 짧음
>* 빠른 일기 및 쓰기 필요



>Apache Cassandra
>
>* Open Source NoSQL DB
>* MasterLess Archiecture
>* High Availability
>* Linearly Scalable
>*  Used by Uber, Netflix, Hulu, Twitter, Facebook



>CAP Theorem
>
>* Consistency : 데이터베이스에서 읽을 때마다 최신(올바른) 데이터 또는 오류를 가져옵니다.
>* Availability : 데이터가 최신 업데이트라는 보장 없이 모든 요청이 수신되고 응답이 제공됩니다.
>* Partition Tolerance : 노드 간 네트워크 연결이 끊어져도 시스템이 계속 작동합니다



>Data Modeling in Apache Cassandara
>
>* Denormailization is not just okay -- 비정규화가 당연
>* Denormailization must be done for fast reads -- 빠른 읽기를 위한 비정규화
>* Apache Cassandra has been optimizaed for fast writes -- 빠른 쓰기에 최적화
>* One table per query is a great starategy -- 쿼리당 하나의 테이블은 휼륭한 전략
>* Apache Cassandra does not allow for JOINs between tables -- 테이블간 JOIN을 허용 하지 않음
>
>![image-20230330110400638](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230330110400638.png)
>



>Cassandra Query Language, CQL
>
>* Cassandra 쿼리 언어는 데이터베이스와 상호 작용하는 방식이며 SQL과 매우 유사합니다. 다음은 CQL에서 지원 하지 않습니다.
>  * JOINS
>  * GROUP BY
>  * Subqueries(하위 쿼리)



>Primary Key
>
>* Must be unique
>* Primary Key는 Partition Key로만 구성되거나 Clustering Columns를 포함할 수 있다.
>* 단순 Primary Key는 Partition Key이기도 한 하나의 열이다. 복합 Primary Key는 둘 이상의 열로 구성되며 고유의 값 생성 및 검색 쿼리에 도움이 된다.
>* Partition Key는 시스템 전체의 데이터 분포를 결정한다.



>Clustering Column
>
>* 클러스터링 열은 정렬된 오름차순으로 데이터를 정렬함
>* 둘 이상의 클러스터링 열을 추가할 수 있음
>
>![image-20230413104857619](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230413104857619.png)
>

>WHERE Clause
>
>* Apache Cassandra의 데이터 모델링은 쿼리 중심이며 WHERE절에 초점을 맞춰야 합니다.



>What we covered in this lesson:
>
>* Basics of Distributed Database Design
>* Must Know your queries and model the tables to your queries (쿼리 중심 모델링)
>* Importance of Denormalization
>* Primary Key, Partition Key, and Clustering Column
>* The WHERE clause


