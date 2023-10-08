경사 하강법(Gradient Descent)은 최적화(Optimization) 알고리즘 중 하나로, 주어진 함수(일반적으로 손실 함수 또는 비용 함수)의 값을 최소화하는 데 사용되는 방법입니다. 아래는 경사 하강법의 엄밀한 정의와 동작 원리를 설명합니다:

1. **목표 함수 (Objective Function)**: 경사 하강법은 주어진 목표 함수 (Objective Function) 또는 손실 함수 ([[Loss Function]])을 최소화하는 것이 목표입니다. 목표 함수는 모델의 파라미터(가중치와 편향)에 대한 입력과 출력 간의 관계를 나타냅니다.
    
2. **파라미터 업데이트**: 경사 하강법은 초기 파라미터 값을 설정한 후, 목표 함수의 그래디언트(기울기)를 계산합니다. 그래디언트는 현재 파라미터에서 목표 함수의 값이 가장 빠르게 감소하는 방향을 나타냅니다.
    
3. **학습률 ([[Learning Rate]])**: 경사 하강법은 학습률(learning rate)이라고 불리는 하이퍼파라미터를 사용합니다. 학습률은 각 스텝에서 그래디언트에 곱해져서 파라미터를 업데이트하는 데 사용됩니다. 적절한 학습률을 선택하는 것이 중요합니다.
    
4. **파라미터 업데이트**: 경사 하강법은 현재 파라미터에서 그래디언트를 빼는 방식으로 파라미터를 업데이트합니다. 이는 목표 함수의 값을 최소화하는 방향으로 파라미터를 이동시킵니다.
    
5. **수렴**: 경사 하강법은 주어진 조건 하에서 (예: 일정한 학습률, 충분한 반복 횟수) 목표 함수가 최소값에 수렴할 때까지 파라미터를 업데이트하며 반복됩니다. 이때 최소값에 도달하면 경사 하강법은 멈추고 최적의 파라미터 값을 반환합니다.
    

경사 하강법은 주로 머신러닝과 딥러닝 모델을 훈련하는 데 사용되며, 손실 함수의 최소값을 찾는 과정에서 파라미터를 조정하여 모델을 학습합니다. 이를 통해 모델은 데이터에 대한 예측을 더 잘 수행하도록 최적화됩니다.

다변수함수의 미분을 통해 $\nabla J_\theta(\theta)$를 구하여 그를 [[Learning Rate]] 와 곱하여 $J(\theta)$ 값에 더하는 것.
$\theta$ = [[model parameter]]
미분값을 계산하는데 [[역전파(Backpropagation)]]을 사용한다.
![[Pasted image 20230929151615.png]]


**손실함수 곡면**
![[Pasted image 20230929174923.png]]
주의)
손실함수 곡면과 분류 곡면은 다르다!!!
분류 곡면 : $y = f(x_1, x_2)$
손실함수 곡면 : $J(\theta)$

~~~python
def train(x, y, model, lr = 0.1):
    dW1 = np.zeros_like(model.W1)
    db1 = np.zeros_like(model.b1)
    dW2 = np.zeros_like(model.W2)
    db2 = np.zeros_like(model.b2)
    m = len(x)
    
    a2, (z1, a1, z2, _) = model.predict(x)
    cost = 0.0
    
    for x, y in zip(X, Y):
        a2, (z1, a1, z2, _) = model.predict(x)
        if y == 1:
            cost -= np.log(a2)
        else:
            cost -= np.log(1 - a2)
            
        diff = a2 - y
        #diff = scala
        db2 += diff
        #dW2 = {R^h}
        dW2 += diff*a1
        #db1 = {R^h}
        #W2 = {R^h}
        #1-a1**2 = {R^h}
        db1 += diff*np.multiply(model.W2, (1 - np.multiply(a1, a1)))
        #dW1 = {R^{h*n}}
        dW1 += diff*np.outer(np.multiply(model.W2,(1 - np.multiply(a1, a1))), x)
    
    cost /= m
    model.W1 -= lr * dW1/m
    model.b1 -= lr * db1/m
    model.W2 -= lr * dW2/m
    model.b2 -= lr * db2/m
    
    return cost
~~~