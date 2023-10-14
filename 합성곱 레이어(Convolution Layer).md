같이보기
- [[합성곱]]
- [[padding]]
- [[stride]]
- [[Fully connected layer vs Convolutional layer]]
- [[합성곱 신경망(Convolutional Neural Network)]]

이미지 분류를 위한 계산 방식. 겉 선을 진행방향대로 딸 수 있다.
필터를 가중치로 보고, 편향은 1로 고정시킨다.

일반적으로 수학에서 합성곱은 해당 커널(필터)를 뒤집지만
CNN에서 합성곱의 필터는 train 가능한 모델 파라미터(특히 Weight)이기 때문에
굳이 커널을 뒤집을 필요는 없다.

### 레이어 내에서의 적용법
1. 이미지의 특성 분류(명도, 채도, RGB값 등)
2. 해당 값 별로 합성곱 적용
3. 그 값들의 결과가 해당 특성 서술하게 됨.
![[Pasted image 20231014002631.png]]

이를 한차원 뒤에서 이용하면 여러개의 필터를 적용할 수 있음.
![[Pasted image 20231014002716.png]]

![[Pasted image 20231014002830.png]]
h : 높이
w : 너비
c : 채널 | 깊이