## Learning Objectives

* NoSQL 데이터베이스를 위한 데이터 모델링 기초
* 비정규화, 기본키, 클러스터링 열 및 WHERE 절

## Non-Relational Databases

NoSQL = Not Only SQL

### When to Use NoSQL

* 높은 가용성이 필요할때
* 많은 양의 데이터를 갖고 있을때
* 선형 확장이 필요할때
* Low Latency가 필요할떄
* 빠른 읽기 쓰기가 필요할때

![](./_image/image1.png)

## Distributed Databases

* 단일 시스템이 아니라 여러 시스템으로 구성된 데이터베이스이다.
* high availability를 유지하려면 데이터 사본이 필요하다. (노드가 실패할수도 있으므로 해당 데이터의 노드의 사본이 필요하다.)
*  데이터가 복제될 수도 있다는 이유때문에 데이터간에 업데이트 차이가 있을수 있고 일관성을 유지하기 위해 Eventual Consistency가 필요하다.

### Eventual Consistency

* 일관성 모델의 하나로, 데이터 항목에 새로운 업데이트가 없으면 궁극적으로 해당 항목에 대한 모든 접근들은 마지막으로 업데이트된 값을 반환하는 것

## CAP

![](./_image/image2.png)



## Denormalization in Apache Cassandra

* 비정규화는 필수다.(3번째 정규화 형식으로는 작동하지 않는다)
* JOIN이 없다.
* 빠른 읽기를 위해선 비정규화를 해야 한다.(아파치 카산드라는 빠른 쓰기에 최적화 되어 있다.)
* 좋은 모델을 만들기위해서 쿼리를 먼저 생각 해야 한다.
* 쿼리당 하나의 테이블을 쓰는거는 좋은 방법이다. (데이터의 복제로 중복 데이터가 생기지만 성능 이점과 고 가용성을 유지하고, 스토리지를 추가하는것 보다 훨씬 이득이다.)

![](./_image/image3.png)

## PRIMARY KEY

* 유니크하다.
* PRIMARY KEY는 PARITION KEY로만 구성되거나 추가 CLUSTERING COLUMNS를 포함 할 수도 있다.
* 단순 PRIMARY KEY는 PARTITION KEY이기도 한 하나의 열이다, 복합 PRIMARY KEY는 둘 이상의 열로 구성되며 고유 한 값을 만들고 검색  쿼리에 도움을 준다.
* PARITION KEY는 시스템 전체의 데이터 배포를 결정한다.

![](./_image/image4.png)

![](./_image/image5.png)
