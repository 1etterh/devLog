---
tags:
  - database
  - modeling
draft: false
---
## 이상(Anomaly)
> 중복된 데이터 때문에 데이터에 의도하지 않은 현상이 발생하는 것 <br/>
> 이상의 종류에는 삽입이상, 갱신이상, 삭제 이상이 있다.


### 삽입이상(Addition Anomaly)
1. Relation에서 새로운 Instance를 삽입할 때 발생하는 데이터 이상현상이다.
2. 불필요한 정보를 함께 저장하지 않고는 어떤 정보를 저장하는 것이 불가능하다.
###### 예시

| 주문번호 | 상품번호 | 상품명 | 단가   | 주문수량 |
| ---- | ---- | --- | ---- | ---- |
| 1001 | P01  | 사과  | 1500 | 2    |
| 1002 | P02  | 바나나 | 2000 | 20   |
위와 같은 테이블에 추가적으로 주문이 들어온 경우
불필요한 중복이 발생하며, 정해지지 않은 값은 NULL로 채워야 한다.

| 주문번호 | 상품번호 | 상품명 | 단가   | 주문수량 |
| ---- | ---- | --- | ---- | ---- |
| 1001 | P01  | 사과  | 1500 | 2    |
| 1002 | P02  | 바나나 | 2000 | 20   |
| 1003 | P01  | 사과  | 1500 | 10   |
| 1004 | P01  | 사과  | 1500 | 15   |
| NULL | P03  | 키위  | 3000 | NULL |



### 갱신이상(Update Anomaly)
1. Relation에서 속성의 값을 업데이트할 때 발생하는 데이터 이상 현상이다.
2. 반복된 데이터 중에 일부만 수정하면 데이터의 불일치가 발생한다.
3. 상품이나 단가와 같은 속성의 값들이 변경될 경우 같은 상품은 빠짐없이 모두 수정해주어야 한다.

| 주문번호 | 상품번호 | 상품명 | 단가     | 주문수량 |
| ---- | ---- | --- | ------ | ---- |
| 1001 | P01  | 사과  | _2500_ | 2    |
| 1002 | P02  | 바나나 | 2000   | 20   |
| 1003 | P01  | 사과  | _2500_ | 10   |
| 1004 | P01  | 사과  | _2500_ | 15   |
| NULL | P03  | 키위  | 3000   | NULL |



### 삭제이상(Deletion Anomaly)
1. Relation에서 인스턴스를 삭제할 때 발생하는 데이터 이상 현상이다.
2. 유용한 정보를 함께 삭제하지 않고는 어떤 정보를 삭제하는 것이 불가능하다.

| 주문번호     | 상품번호    | 상품명    | 단가       | 주문수량     |
| -------- | ------- | ------ | -------- | -------- |
| 1001     | P01     | 사과     | 2500     | 2        |
| 1002     | P02     | 바나나    | 2000     | 20       |
| 1003     | P01     | 사과     | 2500     | 10       |
| 1004     | P01     | 사과     | 2500     | 15       |
| ~~NULL~~ | ~~P03~~ | ~~키위~~ | ~~3000~~ | ~~NULL~~ |
3. 주문 내역을 삭제하면서 키위라는 항목의 가격과 상품 번호가 같이 삭제되어 버리는 이상 현상이 발생한다.