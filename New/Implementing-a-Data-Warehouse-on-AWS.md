#### Implementing a Data Warehouse on AWS

>Learning Outline
>
>* 클라우드에 데이터 웨어하우스를 구축해야 하는 이유
>* Amazon Redshift의 아키텍처
>* Redshift의 ETL 개념
>* Redshift 클러스터 구축
>* Redshift 테이블 설계 최적화

>Amazon Redshift
>
>![image-20230601070854400](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230601070854400.png)
>
>* Redshift는 Column-oriented RDBMS
>* OLAP workloads에 적합
>
>![image-20230601071944294](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230601071944294.png)
>
>* Redshift는 Massively Parallel Processing(MPP) 방식으로 여러 CPU에서 단일 쿼리를 처리한다. 
>* Partitioned 된 Table들을 각 CPU에 분산시켜서  하나의 쿼리로 전체 테이블을 병렬로 처리할 수 있다.
>* 각 CPU는 스토리지를 갖고 있다.
>
>![image-20230601072050740](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230601072050740.png)
>
>* Redshift는 Leader Node 1개와 하나 이상의 Compute Node로 구성된다.
>* Client App은 JDBC, ODBC 같은 프로토콜을 사용하여 Leader Node와 통신한다.
>* Clinet App에서 Leader Node는 일반 데이터베이스와 같다.  
>* Leader Node는 Compute Node의 작업을 명령하고 조정한다.
>* Leader Node는 외부 통신을 처리하고, 쿼리 실행을 최적화 한다.
>* Compute Node에는 자체 CPU가 있다.
>* Compute Node는 논리적으로 여러 조각으로 나뉘어 지고 n개의 슬라이스가 있는 클러스터는 테이블의 n개의 파티션을 동시에 처리할 수 있다.
>* Compute Node의 모든 슬라이스의 합계가 병렬화 단위이다.

>Ingesting Data at Scale
>
>![image-20230601074121879](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230601074121879.png)
>
> ![image-20230601074442332](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230601074442332.png)
>
>* SQL로 옮기는건 너무느려서 복사해서 처리를 한다.
>* 파일을 나눠서  복사 처리를 한다.
>* 나눠서 처리를 하는 경우 공통 접미사를 찾아서 처리를 하든지 공통 접미사를 매니페스트에 입력해 처리를 한다.
>*  너무 큰 파일인 경우에는 압축해서 진행한다. (gzip 형식)
>* Traffic이 발생하므로 Redshift와 같은 Region에 있는 곳에 스테이징한다.
>
>Quiz
>
>* AWS의 ETL 구현에서 EC2 인스턴스의 목적은 무엇입니까?
>  * COPY 명령을 실행하기 위해 RDS 및 Redshift에 대한 클라이언트 역활을 하는 기계

>Optimizing Table Design
>
>* Distribution Style
>  * EVEN distribution: 짝수, 라운드 로빈 배포 스타일로 고르게 분포시킴
>  * ALL distribution: 작은 테이블일 경우 나누지 않고 모두에게 배포해서 셔플링을 줄임
>  * AUTO distribution: EVEN, ALL 을 자동으로 배포
>  * KEY distribution: 유사한 키값으로 배포
>* Sorting key: Column을 키로 지정해 정렬시키고 배포
>
>![image-20230605075642650](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230605075642650.png)
>
>![image-20230605075711987](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230605075711987.png)
>
>![image-20230605075818126](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230605075818126.png)
>
>![image-20230605075842397](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230605075842397.png)
>
>![image-20230605080340332](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230605080340332.png)

>Lesson Review
>
>* 아마존 레드시프트 아키텍처
>* Redshift로 ETL하는 방법
>* S3 버킷을 사용하여 Redshift로 데이터를 수집하는 방법
>* 병렬 ETL
>* 분산 스타일을 사용하여 테이블 디자인 최적화
