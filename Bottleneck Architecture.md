![[Pasted image 20231101201717.png]]

256 채널을 필터를 이용해 64채널까지 감소시켰다가
다시 256채널로 증가시키는 것.
필요한 매개변수의 수가 대폭 감소된 것 확인 가능

![[Pasted image 20231101201811.png]]
위 사진에서는 50레이어 이후부터가 bottlenect 구조를 사용한 모델이다.
[[FLOPs]]을 보면 계산횟수도 실제로 크게 증가하지 않은것을 볼 수 있다.