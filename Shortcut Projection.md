$a^{[l]}$과 $a^{[l+2]}$ 의 차원이 다를때 이용하는 기법 

![[Pasted image 20231101200832.png]]


- 너비와 높이 일치시키는 방법 : [[stride]]

- 채널의 깊이 일치시키는 방법 : $1\times1$ convolution filter 의 개수 조절 -> 깊이 D가 필터의 개수에 의해 결정됨!

- 위 두가지를 잘 조합한 행렬이 $W_s$