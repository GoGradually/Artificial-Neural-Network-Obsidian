2015년에 마이크로소프트에서 발표한 새로운 이미지 인식 신경망.
이걸로 이제 신경망이 사람보다 인식률이 뛰어나게 되었다.

핵심 기술로는 [[skip-connection]], [[Bottleneck Architecture]] 가 있다.

### ResNet이 중요한 두가지 이유
- 성능-> 뛰어남
- [[Residual Learning Framework]] -> [[Transformers]] 에도 이용됨

### ResNet 의 특징
- 152 개의 레이어를 가진 매우 깊은 신경망
- 기울기 소실로 인해 Underfitting되는 문제를 해결할 수 있게됨.
- [[Residual Block]] 안에 존재하는 레이어끼리 [[skip-connection]]을 이용하여 레이어를 지우는 효과를 가져올 수 있음.
- 최종적으로 Fully connected Layer 대신 [[Global Average Pooling]] 을 이용하여 레이어를 flattening 시킴.
- Train 값과 Test값을 모두 감소시킴으로써 과소적합을 막을 수 있게됨.
- 연산 횟수를 감소시키기 위한 [[Bottleneck Architecture]]를 사용한다.