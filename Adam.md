[[RMSprop]] + [[Momentum]]
가장 많이 쓰게 될 최적화 방법

![[Pasted image 20231003003701.png]]

RMSprop과 Momentum 은 각자 독립적으로 적용할 수 있다.



수도코드![[Pasted image 20231003003842.png]]


1. 초기 m, v, t값 설정
2. 반복문 시작
   - g = 이전 그라디언트
   - m 설정 (베타 1)
   - v 설정 (베타 2)
   - m hat 설정 (mt / (1 - beta1t))
   - v hat 설정 (vt / (1 - beta2t))
   - 매개변수 업데이트
 -> RMSprop 과 Momentum 이 각자 독립적으로 적용됨