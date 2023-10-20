batch : 일괄, 한꺼번에 처리
emperical : 경험적인
[[Regularization vs Normalization]]
[[input normalization vs batch normalization]]

몇몇 레이어에 활성화 함수를 한꺼번에 처리하는 것을 고려하는 것.
(레이어 별 연산)

활성함수의 입력 데이터의 분포를 평균이 0, 분산이 1이 되도록 정규화 시키는 것.
평균이 0 : zero-mean
분산이 1 : unit-variance

레이어의 입력 데이터에 대해 평균 및 분산을 계산하고, 이를 사용하여 데이터를 정규화한 다음 확대 및 이동(scale and shift) 파라미터를 적용합니다.
->이로써 각 레이어의 활성화 값을 안정화하고 학습 과정을 개선시킵니다.

### 정규화 과정
1. 정규화 $$\hat{x}^{(k)} = \frac{x^{(k)}-E[x^{(k)}]}{\sqrt{Var[x^{(k)}]}}$$정규화 시 평균은 0, 분산은 1이 되도록 값 변화됨
2. 확대 및 이동$$\hat{y}^{(k)} = \gamma^{(k)}\hat{x}^{(k)} + \beta^{(k)}$$$\gamma$ = 확대
   $\beta$ = 이동
   $\gamma$와 $\beta$ 모두 학습이 가능한 값

### 정규화 위치
레이어의 사이사이에 들어가는 정규화 방법
선형회귀 뒤에 활성화함수 들어가기 전에 정규화
![[Pasted image 20231020125729.png]]

### 수도 코드
![[Pasted image 20231020125947.png]]
주의 : test phase 에서는 다르다
미니배치에서의 [[Exponentially weighted averages]]를 이용하여 평균과 분산을 추정한다

### 배치 정규화의 장점
- 신경망의 학습속도를 가속시킨다.
- 높은 학습률을 적용 가능하게 한다.
- 초기 가중치에 건장하게? 영향받는다 (통계에서의 Robust)
- [[정규화(Regularization)]]를 하는 효과를 줄 수 있다.
- 보통 더 좋은 결과를 가져다 준다
- 일반적으로 배치 정규화는 [[드롭아웃]]했을 때의 효과를 그대로 가져오기 때문에 둘을 같이 사용하지는 않는다.
  ![[Pasted image 20231020132134.png]]