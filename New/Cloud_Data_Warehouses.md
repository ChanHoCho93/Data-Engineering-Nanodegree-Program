#### Cloud Data Warehouses

>Learning Outline
>
>* Introduction to ETL
>* ELT vs ETL
>* When to use ELT
>* Cloud SQL Storage
>* Cloud NoSQL Storage
>* Cloud ETL Pipeline Services
>* Cloud Streaming Pipeline Services
>* Cloud Data Warehouse Solution

>Expert Perspective: Cloud Data Warehouses
>
>* Scalability
>* Flexibility
>* Cost shifting

>ELT originated from ETL
>
>* ETL: 중간 서버에서 변환이 발생
>* ELT:  대상 서버에서 변환이 발생
>
>ELT
>
>* 확장성: 대량의 데이터를 비교적 쉽게 데이터 웨어하우스 환경에 로드할 수 있습니다.
>* 유연성: 변환 단계는 데이터 웨어하우스가 실행되는 것과 동일한 기술 스택을 사용하여 수행되므로 비지니스 요구 사항이 변경됨에 따라 프로세스의 유연성이 향상됩니다.
>* Cost shifting: 변환 단계는 종종 가장 비용이 많이 들며 마지막으로 수행함으로써 데이터 엔지니어는 Just In Time 변환을 수행하여 우선 순위가 가장 높은 비지니스 요구 사항을 먼저 충족할 수 있습니다.
>* 대규모 데이터 세트의 성능 향상
>* 구조화되지 않은(NoSQL) 데이터 세트에 대한 유연성 향상

>Cloud Managed SQL Storage
>
>* UNMANAGED
>  * Oracle
>  * Microsoft SQL Server
>  * PostgreSQL
>  * MySQL
>  * MariaDB
>* MANAGED
>  * Microsoft Azure
>  * Azure SQL Database (MS SQL Server)
>  * Azure Database for MySQL, MariaDB, PostgreSQL
>  * GCP, Cloud SQL(MySQL, PostgreSQL, MS SQL Server)
>  * AWS, Amazon RDS(MySQL, postgreSQL, MariaDB, Oracle, MS SQL Server)

>Cloud Managed NoSQL Storage
>
>* Azure - CosmosDB
>  * Gremlin - graph database
>  * MongoDB - document
>  * Cassandra - column oriented
>* GCP
>  * Big Table - column oriented
>  * Firestore - documnet
>  * MongDB Atlas - documnet
>* AWS
>  * DynamoDB - Key value
>  * DocumnetDB - document
>  * Keyspaces - Column oriented
>  * Neptune - graph
>  * Time stream - time series

>Cloud ETL Pipeline Services
>
>* ETL / ELT cloud-based tools Major Cloud Providers
>  * Azure Data Factory
>  * AWS Glue
>  * GCP Dataflow
>* Streaming Data:
>  * Azure - Streaming Analytics
>  * AWS - Kinesis
>  * GCP - Dataflow
>    

>* Cloud Data Warehouse Solutions: Cloud Providers
>  * Azure Synapse
>  * Amazon Redshift
>  * GCP Big Query

>클라우드에 구축된 데이터 웨어하우스 솔루션의 구성요소를 다뤘습니다. 클라우드 데이터 웨어하우스로 작업할 때 다음에 대한 결정을 내려야 합니다.
>
>- ETL 및 ELT 기술 사용
>- 클라우드에서 관계형 및 NoSQL 데이터베이스 사용
>- ETL 및 ELT 프로세스에서 데이터 웨어하우스를 통해 데이터를 이동하는 파이프라인
