---
tags:
  - database
  - modeling
---
## 논리모델(Logical Model)
> 개념 모델을 상세화하는 작업으로 전체 속성을 도출하고 도출되지 않은 대부분의 엔티티들과 관계들을 도출하는 단계이다.<br/>
> [[Normalization|정규화]](Normalization)을 진행하는 단계이다.


### 논리 모델의 목적
1. 업무에 대해 충분히 의견을 교환하고 반영하여 진행하는데 도움을 준다.
2. 중복값을 제거하여 이상([[Anomaly]]) 현상을 제거하기 위해 속성간에 종속관계를 확인하고 엔터티를 분할한다.

### 논리모델의 주의사항
1. 업무 요건을 빠짐없이 정확하게 반영해야 한다.
2. 더 이상 삭제할 엔터티나 속성은 없어야 한다.
3. 주 식별자에 있어 효율성에 따라 인조 식별자를 채택할 지에 대해 결정한다.
4. 지나치게 성능 문제를 해결하려고 하지 않는다.