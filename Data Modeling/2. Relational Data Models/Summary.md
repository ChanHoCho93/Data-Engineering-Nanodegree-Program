## Database

데이터베이스는 관련 데이터의 집합이며 구성 방식이다.

데이터에 대한 엑세스는 일반적으로 데이터베이스 관리 시스템에 의해 제공된다.

### Database Management System

데이터베이스와 상호 작용하고 모든 데이터에 대한 액세스를 제공할 수 있는 사용자로 부터 구성된 컴퓨터 소프트웨어

### Importance of Relational Databases

#### Relational Importance

* Standardization of data model (데이터 모델의 표준화)
* Flexibility in adding and altering tables (테이블 추가 및 변경의 유연성()
* Data Intergrity (데이터 무결성)
* Standard Query Language (SQL)
* Simplicity (간단)
* Intuitive Organization (직관적인 구성)

### OLAP vs OLTP

* OLAP (Online Analytical Processing):

    사용자의 의사결정에 도움이 되는 데이터들을 분석한다. OLAP는 단독으로 존재하는 정보 시스템이 아니며 데이터 웨어하우스나 데이터 마트 같은 시스템과 상호 연관 되며, 조회,계산,시계열 등 복잡한 모델링까지 다양한 각도에서 전략적인 정보로 변환시키는 역활을 한다.

* OLTP(Online Transactional Processing):

  네트워크상의 여러 이용자가 실시간으로 데이터베이스의 데이터를 갱신하거나 조회하는 등의 단위 작업을 처리하는 방식을 말한다.

### Structuring the Database: Normalization

* Normalization:

  관계형 데이터베이스의 설계에서 데이터를 구조화 하는 프로세스를 말하며 데이터의 중복을 줄이고 데이터의 무결성을 높이기 위해 한다.

* Denormalization: 

  Normalization된 데이터베이스에서 성능을 개선하기 위해 사용되는 전략으로, 일부 쓰기 성능의 손실을 감수하고 데이터를 묶거나 데이터의 복제 사본을 추가함으로써 데이터베이스의 읽기 성능을 개선하려고 시도하는 과정이다.

### Objectives of Normal Form

* 삽입, 업데이트, 제거들의 종속성으로부터 데이터베이스는 자유로워야 한다.
* 새로운 타입의 데이터가 올때마다 리팩토링할 필요가 없게 해야 한다.
* 관계형 모델을 사용자에게 더 유익하게 한다.
* 데이터베이스의 쿼리를 가용성 있게 만든다.

### Normal Forms

* 제1정규형 (1NF)    
    - 원자성, 모든 속성은 반드시 하나의 값만 가져야 한다.    
* 제2정규형 (2NF)    
    - 부분 종속, 모든 속성은 반드시 모든 기본키에 종속되어야 한다.(기본키 일부에만 종속되어서는 안됨)    
* 제3정규형 (3NF)    
    - 이행 종속, 기본키가 아닌 모든 속성간에는 서로 종속될 수 없다.

### Denormalization
 * 데이터베이스의 JOINS는 뛰어난 유연성을 제공하지만 매우 느리기때문에 데이터베이스에서 과도한 읽기를 처리하는 경우 테이블 Denormalization을 고려할 수 있다.
* 데이터를 Normalization된 형식으로 가져온다음 Denormalization을 진행한다. 따라서 Denormalization은 Normalization 후에 발생 한다.

### Fact and Dimension Tables
* Fact table은 Dimension table들의 기본키로 구성되며 Star Schema 또는 Snowflake Schema 의 중심에 있는 테이블이다.

* Dimension table은 Fact table의 값을 한정해서 보여주는 테이블이며 쿼리 필터링,제한,그룹핑 역활을 한다.

![](./_image/2020-12-15-18-09-11.jpg)









