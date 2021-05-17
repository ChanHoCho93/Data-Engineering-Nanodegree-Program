# Optimizing Table Design

- Distribution Styles
- Sorting Key

쿼리 속도올리기 위해 테이블 최적화 방법에 대해 알아보겠습니다.  중요 쟁점은 `Shuffling` 이라고 불리는 테이블간의 참조를 어떻게 처리할 것인가 입니다.

## Distribution Styles

Distribution Styles에는 `EVEN, ALL, AUTO, KEY`  4가지 방식이 있습니다. 

#### EVEN Distribution

![image-20210419104919402](_image\image-20210419104919402.png)

EVEN Distribution은 `Fact, Dimention Table`의 Row를 각 CPU에 `Load-Balancing` 합니다. 눈여겨 볼점은 Row를 순차적으로 Copy를 하는 것입니다.  이러한 방식은 Join이 많이 필요없는 테이블에  강점을 가지고, 반대로 Join이 많이 필요하게되면 테이블간의 참조가 많아지므로 Shuffling이 많이 발생하게 됩니다. 위 색깔 화살표처럼 Store를 참조하기 위한 Network Traffic이 많이 발생하고 있습니다.

#### ALL Distribution

![image-20210419110422799](_image\image-20210419110422799.png)

ALL Distribution은 각 CPU에 Table 전체를 Copy하는 것입니다. 위 이미지에서 Fact Table은 EVEN, Dimention Table은 ALL Distribution 방식으로 진행을 하게 됨으로써 다른 테이블을 참조할 필요없이 로컬내에서 참조 가능하므로 Shuffling이 발생하지 않습니다. 이러한 방식이 저장소 낭비, 효율적이지 않을수 있지만, 보통 Dimention Table은 작기 때문에 큰 상관이 없고, Shuffling이 발생하는것보다 더 효율적이기 때문에 괜찮습니다.

#### AUTO Distribution

![image-20210419111048754](_image\image-20210419111048754.png)

AUTO Distribution은 Redshift가 자동으로 관리해주는 방식입니다. Redshift 기준에서 Small Table은 ALL, Large Table는 EVEN 방식으로 관리하게 됩니다.

#### KEY Distribution 

![image-20210419112030281](_image\image-20210419112030281.png)

KEY Distribution은 Fact Table의 Columms들중 하나를 선택하여 같은 값끼리 CPU에 Copy하는 방식입니다. 위 이미지에서 dimStore를 기준으로 CPU에 Copy되고 있습니다. ALL Distribution과 마찬가지로 Shuffling이 일어나지 않지만 ALL Distribution에서 Dimention Table을 Copy할때 Table이 너무 커서 문제가 생길경우 KEY Distribution이 좋은 대안이 될수 있습니다.

## Sorting Key

![image-20210419115049618](_image\image-20210419115049618.png)

Sorting Key는 Columm하나를 Key로 지정하고 특정범위 만큼 CPU에 Copy하는 방식입니다. Shuffing이 발생하지 않으며 내부에 미리 정렬되어 있으므로 Query 성능이 좋아지게 됩니다.




