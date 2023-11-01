![[Pasted image 20231101195048.png]]

이전 레이어의 값이 그대로 중간에 들어오는 블록.
[[skip-connection]]의 활용으로 활성함수에 들어가기 이전에 이전 블록의 출력값이 그대로 더해짐.
-> 레이어의 수를 줄임으로써 SNN처럼 동작하게 만듬.


### 실제 동작 방식
![[Pasted image 20231101195747.png]]

1) $3\times3$ convolution filters
2) [[배치 정규화(Batch Normalization)]]
3) [[ReLU]] Activation

a(l) 과 a(l+2)의 차원이 다를 때 : [[Shortcut Projection]]
