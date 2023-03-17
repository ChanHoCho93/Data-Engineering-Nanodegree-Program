#### Relational Data Models

>Learning Objective
>
>* Normalization
>* Denormalization
>* Fact/dimenstion tables
>* Different schema models



>Database Definition
>
>* 관련 데이터 집합 및 구성 방식
>* 데이터에 대한 액세스는 일반적으로 데이터베이스 관리 시스템에서 제공
>
>* DBMS란 DB와 상호 작용하고 모든 해당 데이터에 대한 액세스를 제공하는 소프트웨어
>
>[RDBMS  Codd 12Rules][https://en.wikipedia.org/wiki/Codd%27s_12_rules]



>Importance of Relational Databases
>
>* Standardization of data model : 데이터가 행과 열 형식으로 변환되면 데이터가 표준화되고 SQL로 쿼리할 수 있습니다.
>* Flexibility in adding and altering tables : 관계형 데이터베이스는 테이블 추가, 테이블 변경, 데이터 추가 및 제거에 대한 유연성을 제공합니다.
>* Data Intergrity : 데이터 무결성은 관계형 데이터베이스 사용의 중추입니다.
>* Structured Query Language(SQL) : 미리 정의된 언어로 데이터에 액세스하기 위해 표준 언어를 사용할 수 있습니다.
>* Simplicity : 데이터가 체계적으로 저장되고 표 형식으로 모델링됩니다.
>* Intuitive Organization : 스프레드시트 형식은 직관적이지만 관계형 데이터베이스의 데이터 모델링에 직관적입니다.



>OLAP vs OLTP
>
>[OLAP vs OLTP stackoverflow][https://stackoverflow.com/questions/21900185/what-are-oltp-and-olap-what-is-the-difference-between-them]
>
>* **OLTP** (On-line Transaction Processing)는 특정 시스템의 운영에 관여합니다. OLTP는 다수의 짧은 온라인 트랜잭션(INSERT, UPDATE, DELETE)이 특징입니다. OLTP 시스템의 주요 강조점은 매우 빠른 쿼리 처리, 다중 액세스 환경에서 데이터 무결성 유지 및 초당 트랜잭션 수로 측정되는 효율성입니다. OLTP 데이터베이스에는 상세하고 최신 데이터가 있으며 트랜잭션 데이터베이스를 저장하는 데 사용되는 스키마는 엔티티 모델(보통 3NF)입니다. 여기에는 회사 데이터베이스에서 이메일 업데이트와 같은 개별 레코드에 액세스하는 쿼리가 포함됩니다.
>* **OLAP** (On-line Analytical Processing)는 기록 데이터 또는 보관 데이터를 처리합니다. OLAP는 거래량이 상대적으로 적은 것이 특징입니다. 쿼리는 종종 매우 복잡하고 집계를 포함합니다. OLAP 시스템의 경우 응답 시간은 효율성 척도입니다. OLAP 응용 프로그램은 데이터 마이닝 기술에서 널리 사용됩니다. OLAP 데이터베이스에는 다차원 스키마(일반적으로 스타 스키마)에 저장된 집계된 기록 데이터가 있습니다. 때때로 쿼리는 작년에 회사의 이익이 무엇인지와 같은 관리 레코드의 많은 양의 데이터에 액세스해야 합니다.
>* OLAP와 OLTP의 차이점을 기억하는 핵심은 분석(A) 대 트랜잭션(T)입니다. 신발 가격을 확인하려면 OLTP를 사용하고 있는 것입니다(집계가 거의 없거나 전혀 없음). 특정 매장에서 판매한 신발의 총 재고를 알고 싶다면 OLAP를 사용해야 합니다(집계가 필요하기 때문).
>



>Normalization and Denormalization
>
>* Normalization: To reduce data redundancy and increase data integrity.
>* Denormalization: Must be done in read heavy workloads to increase performance.



>Objectives of Normal Form
>
>* To free the database from unwanted insertions, updates, & deletion dependencies
>* To reduce the need for refactoring the database as new types of data are introduced
>* To make the relational model more informative to users
>* To make the database neutral to the query statistics



>Normal Forms
>
>* 1NF
>
>  * Atomic values: each cell contains unique and single values
>
>  * Be able to add data without altering tables
>
>  * Separate different relations into different tables
>
>  * Keep relationships between tables together with foreign keys
>
>* 2NF
>
>  * All columns in the table must rely on the Primary Key
>
>* 3NF
>
>  * No transitive dependencies, Remember, transitive dependencies you are trying to maintain is that to get from A-> C, you want to avoid going through B.
>



>Denormalization
>
>* The Designer is incharge of keeping data consistent
>* Reads will be faster (select)
>* Writes will be slower (insert, update, delete)
>
>
>
>
>
>
>
>
