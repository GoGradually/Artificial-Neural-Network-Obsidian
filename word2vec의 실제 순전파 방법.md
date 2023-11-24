
![[word2vec_skip-gram.png]]
1) 현재 입력 단어를 one-hot vector x로 받는다
2) 학습시킨 model parameter 인 $W_{input}$ 을 x와 곱한다.
   이 때, W는 transpose 한다. $(h = w_{input}^Tx)$
3) 해당 연산을 한 결과값 h 가 hidden state 가 된다.
4) 학습시킨 model parameter 인 $W_{output}$ 을 h와 곱한다.
5) 해당 결과값이 $\hat y$ 벡터가 된다.


$W_{input}$ = word embedding 을 만들기 위한 매트릭스. 편향 b = 0.
해당 word embedding 이 hidden state 역할을 하게 된다

$W_{output}$ = 실제 단어가 등장할 확률을 계산하기 위한 매트릭스.



선형 레이어 두개가 있다. $W_{in}$ $W_{out}$
