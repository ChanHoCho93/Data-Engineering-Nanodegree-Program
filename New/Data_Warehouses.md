#### NoSQL Data Models

>Learning Objective
>
>* Business Needs for Data Analytics
>* Data Warehouse Design
>* Data Warehouse Architecture
>* OLAP Cubes



>What is a Data Warehouse? A Business Perspective
>
>* 고객이 상품을 찾고 주문할 수 있어야 합니다.
>* Inventory Staff(재고관리 직원?)는 상품을 보관, 검색 및 재주문할 수 있어야 합니다.
>* Delivery Staff는 상품을 픽업 및 배송할 수 있어야 합니다.
>* HR은 영업 직원의 성과를 평가할 수 있어야 합니다.
>* Marketing should be able to see the effect of different sales channels
>* 경영진은 매출 성장을 모니터링할 수 있어야 합니다.
>
>Details that may affect your data infrastructure.
>
>* Scale
>* Complexity
>* Tabular data sources
>* Performance
>* Clear requirments

>Operational vs Analytical Business Processes
>
>* Operational processes: Make it works
>  * Find goods & make orders (for customers)
>  * Stock and find goods (for inventory staff)
>  * Pick up & deliver goods (for delivery staff)
>* Analytical processes: What is going on?
>  * Assess the performance of sales staff (for HR)
>  * See the effect of different sales channels (for marketing)
>  * Monitor sales growth (for management)
>
>OLTP and OLAP
>
>![image-20230510080102009](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230510080102009.png)

>Data Warehouse: Technical Perspective
>
>* 운영에 사용되는 소스 시스템에서 데이터를 추출하고 데이터를 변환하여 Demension Model로 로드
>
>Kimball's Bus Architecture
>
>![image-20230512073502313](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230512073502313.png)
>
>DWH: Tech Perspective
>
>![image-20230512073525477](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20230512073525477.png)
>
>ETL: A Closer Look
>
>* Extracting:
>  * Transfer data to the warehouse
>* Transforming:
>  * Integrates many sources together
>  * Possibly cleaning: inconsistencies, duplication, missing values, etc..
>  * Possibly producing diagnostic metadata
>* Loading:
>  * Structuring and loading the data into the dimensional data model
>
>Dimensional Model Review
>
>* Goals of the Star Schema
>  * Easy to understand
>  * Fast analytical query performance
>* Fact Tables
>  * 주문, 전화 통화, 리뷰와 같은 비지니스 이벤트 기록
>  * 팩트 테이블 열은 항목 수량, 통화 시간, 리뷰와 같은 정량화 가능한 메트릭에 기록된 이벤트를 기록
>* Dimension Tables
>  * 누가, 무엇을, 어디서, 왜 등 비지니스 이벤트 컨텍스트를 기록합니다.
>  * 차원 테이블 열에는 항목을 구매한 매장 또는 전화를 건 고객 등과 같은 속성이 포함됩니다.
>
>Example: The DVD Rentals Sample Database
>
>![pagila-3nf](C:\Users\user\Desktop\Git\Data-Engineering-Nanodegree-Program\New\pagila-3nf.png)
>
>![pagila-star](C:\Users\user\Desktop\Git\Data-Engineering-Nanodegree-Program\New\pagila-star.png)

>
>
>
>
>
