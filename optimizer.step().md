최적화된 가중치 업데이트
~~~python
import torch
import torch.optim as optim

# 모델 정의
model = ...

# 손실 함수 정의
criterion = ...

# 최적화기(optimizer) 설정
optimizer = optim.SGD(model.parameters(), lr=0.01)

# 학습 반복
for epoch in range(num_epochs):
    # forward pass
    outputs = model(inputs)
    loss = criterion(outputs, labels)
    
    # 역전파 및 가중치 업데이트
    optimizer.zero_grad()  # 그래디언트 초기화
    loss.backward()  # 역전파 계산
    optimizer.step()  # 가중치 업데이트

~~~