[[RNN 의 기울기 소실]] 문제를 해결하기 위해 나온 모델.
이전 입력값을 바로 다음 입력으로 보낸다. (Like [[skip-connection]])
![[Pasted image 20231116141645.png]]
![[Pasted image 20231116142338.png]]


사전지식) [[gate]]
3개의 게이트로 구성된다.
- [[forget gate]]
- [[input gate]]
- [[output gate]]

hidden state 대신에
- short term state (기본, 은닉상태 역할)
- long term state (추가됨)
가 추가되었다.

총 결과값으로
- [[output&hidden state]]
- [[Long term state]]
가 나온다.


$c_t$ 는 극단적으로 가면
$c_t = c_{t-1}$
$c_t = g_t$ 
이렇게까지 나올 수 있다.