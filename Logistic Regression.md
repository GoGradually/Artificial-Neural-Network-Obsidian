회귀 문제로 분류 문제를 작성하는 방법

선형 회귀에 [[시그모이드(Sigmoid) 함수]] 함수를 적용한 형태.

[[Loss Function]] of Logistic Regression

$$L(\hat{y}, y) = -ylog(\hat{y}) - (1-y)log(1-\hat{y})$$

[[Cost Function]] of Logistic Regression
$$J(w, b) = \frac{1}{m}\displaystyle\sum_{i=1}^{m}L(\hat{y}^{(i)}, y^{(i)})$$
Derivative of Logistic Regression -> [[역전파(Backpropagation)]]에 응용
![[Pasted image 20230929152918.png]]