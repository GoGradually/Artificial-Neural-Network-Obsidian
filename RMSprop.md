Root Mean Square Propagation
양 축 중 한쪽 축의 학습 필요 거리가 더 길 때
[[Learning Rate]]를 조절하여 그라디언트의 크기를 조절하는 것.
[[Exponentially weighted averages]]의 응용인 
지수 가중 이동 평균(Exponential Moving Average)를 사용한다.
$s_{dW}$ 와 $s_{db}$ 를 계산하여 그들의 제곱근을 학습률에 나눈다.


비용 함수의 그래프를 스케일링하는 효과를 가진다
![[Pasted image 20231003003244.png]]
$s_{dW}$ 와 $s_{db}$ 를 계산할 때 각 행렬이 원소별 제곱이라는 사실을 유념하자