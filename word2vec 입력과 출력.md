![[Pasted image 20231117160707.png]]

현재 단어 : 왼쪽
주변 단어 : 오른쪽
순서대로 하나씩 나열하면서 4개의 Training sample 을 만든다.

![[Pasted image 20231117161203.png]]

현재 word embedding 이 입력으로 주어졌을 때
softmax Layer 를 통과하면서 현재 단어 c에 대한 target 단어 t[i] 가 등장할 확률을 $\hat y$ 로 갖는다.

해당 함수의 softmax
$$p(t|c) = \frac{e^{\theta_t^Tw_c}}{\sum_{j=1}^{10000}e^{\theta_j^Tw_c}}$$
Loss function
$$L(y, \hat y) = - \sum_{i=1}^{10000}y_ilog\hat y_i$$
