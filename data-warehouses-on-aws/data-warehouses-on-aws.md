# Data Warehouse On AWS

- Conceptual model in data warehouse
- Implementing DWH (Cloud vs On-Premise)
- DWH Dimensional Model Storage on AWS

## Conceptual model in data warehouse

`Amazone web service`에 들어가기 앞서 DWH의 개념적 모델을 살펴보도록 하겠습니다. 개념적 모델은 크게 Data Sources`, `ETL`, `DWH`, `BI  4가지로 구성됩니다. 구성을 자세히 살펴 보겠습니다.	

#### Data Sources

![스크린샷 2021-02-21 오후 4.44.47](./_image/스크린샷 2021-02-21 오후 4.44.47.png)

OLTP 환경에서 각각의  DB로 데이터가 넘어가는 과정입니다.  이 데이터들은 서로 다른 Operational Processes 들의 DB이기 때문에 높은 이질성(high heterogeneity)을 갖게 됩니다. 

#### ETL

![스크린샷 2021-02-21 오후 5.04.09](./_image/스크린샷 2021-02-21 오후 5.04.09.png)

data sources에서 dimensional model로 넘어가는 과정입니다. 이 과정은 ETL 그리드, 그리드 머신이라고 불리는 머신이 데이터 복사를 위한 많은 schedules 와 pipeline process가 진행되게 됩니다.

#### DWH

![스크린샷 2021-02-21 오후 5.13.25](./_image/스크린샷 2021-02-21 오후 5.13.25.png)

DWH의 저장 과정입니다. ETL을 통해 가공된 데이터 소스들이 diensional model을 통해 저장 되게됩니다. dimensional model에 따라 olap-cube가 될 수 도 있고 다양한 workloads가 될 수 있습니다.

#### BI

![스크린샷 2021-02-21 오후 5.27.22](./_image/스크린샷 2021-02-21 오후 5.27.22.png)

마지막으로 BI-app 또는 visualization 하는 과정입니다. 이 과정을 하고난 후에 비니지스 유저들이 데이터를 통한 작업을 하게 됩니다. 



## Implementing DWH (Cloud vs On-Premise)

DWH의 개념적 모델을 살펴봤고 이제 DWH 구현 방법에 대해 알아보겠습니다.  DWH 구현에는 기본적으로 `Cloud, On-Premise` 2가지 방법이 있습니다. 저희는 AWS를 통한 Cloud 방법으로 구현을 하겠지만 On-Premise의 특성도 알아두면 좋으므로 같이 알아보겠습니다.

#### On-Premise

![스크린샷 2021-02-21 오후 5.52.10](./_image/스크린샷 2021-02-21 오후 5.52.10.png)

On-premise란 서버를 클라우드 같은 원격 환경에서 운영하는 방식이 아닌, 자체적으로 보유한 전산실 서버에 직접 설치해 운영하는 방식입니다. On-premise로 운영하게 되면 heterogeneity, scalability, elasticity등등 여러 고려 할점이 많이 필요합니다. 이런 고려는 개발자 입장에서 하게 되므로 여러 개발자들의 능력도 고려되야 합니다. 여러 개발자들, 서버 장비 등등 모든 자원은 돈이 필요하므로 돈이 가장 중요해 보입니다.

#### Cloud

![스크린샷 2021-02-21 오후 6.00.26](./_image/스크린샷 2021-02-21 오후 6.00.26.png)

Cloud 방식으로 가게되면 On-Premise에 비해 진입장벽이 낮고 사용자 의견에 따라 리소스 추가,제거가 간단합니다. 단점으론 클라우드 서버 운영 비용이 비싸고 Cloud라는 특성상 heterogeneity 문제를 항상 안고 가야하는데 동종 cloud를 사용하게 되면 설정 및 설치, 동일한 작동 등등 간단히 말해 쓰기가 쉽습니다. 하지만 해당 클라우드 업체와 디펜던시가 강해지므로 독립하기가 어려워 집니다. 

heterogeneity/complexity 자료는 [여기](https://www.bmc.com/blogs/homogeneous-vs-heterogeneous-clouds/)를 더 참고하세요.



## DWH Dimensional Model Storage on AWS

Cloud 방식으로 DWH를 구현하므로 AWS의 `Dimensioanl Model Storage `들을 살펴 보도록 하겠습니다.

![스크린샷 2021-02-21 오후 6.24.06](./_image/스크린샷 2021-02-21 오후 6.24.06.png)

#### Cloud-Managed

- 전문가들의 기술을 재사용
- 적은 직원들로 인한 장점(보안, 능력, 운영비용)
- 복잡한 기술에 대한 모든 리소스를 스크립팅 할 수있는 코드 (Infrastructure)
- 이미 존재하기 때문에 사용할 수 없는 기능이 존재할 수가 있음 (비슷한 기능은 존재하지만 세부 설정,지정등이 안될때)

#### Self-Managed

- EC2를 사용한 필요한 모든 기능 구현 가능
- Cloud-Managed가 갖는 장점을 갖지 못함

