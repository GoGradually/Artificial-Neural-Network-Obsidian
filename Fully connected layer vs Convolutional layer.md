일단 둘 다 레이어가 스택처럼 쌓일 수 있다.

### Convolutional layer
1. Tensor -> Tensor
2. 매개변수 : filter, bias
3. Convolution kernels은 input에 sliding window로 접근
4. 매개변수들이 input에 대하여 공유됨
### Fully connected layer
1. vector -> vector
2. 매개변수 : 가중치, bias
3. 레이어 내의 모든 뉴런은 이전 레이어의 모든 뉴런과 연결됨
4. 매개변수들이 input에 대하여 공유되어지지 않음.
### chat GPT 대답
1. **입력 유형:** Fully connected layer는 입력 데이터를 1차원 벡터로 평탄화하여 사용합니다. 반면, Convolutional layer는 2D 또는 3D 입력 데이터를 처리할 수 있으며, 공간 정보를 보존하는 특징 맵(feature map)을 생성합니다.
    
2. **가중치 공유와 공간적 계층 구조:** Convolutional layer는 가중치 공유 및 공간적 계층 구조를 통해 입력의 지역 패턴을 감지하는 데 특화되어 있습니다. Fully connected layer는 입력 간에 가중치가 공유되지 않으며, 데이터의 공간적 구조를 무시합니다.
    
3. **계산 효율성:** Convolutional layer는 합성곱 연산을 사용하여 특징 맵 간의 연결을 효율적으로 처리합니다. 이로써 Convolutional layer는 학습 가능한 매개변수 수가 적고, 공간적 계층 구조를 고려하여 특징을 추출할 수 있습니다. Fully connected layer는 입력과 출력 간의 모든 가능한 연결을 가지므로 매개변수 수가 많아질 수 있습니다.
    
4. **용도:** Convolutional layer는 주로 이미지 및 비디오와 같은 2D 미디어 데이터에서 특징을 추출하는 데 사용됩니다. Fully connected layer는 특징 추출된 데이터를 기반으로 최종 분류 또는 회귀 작업을 수행하는 데 사용됩니다.