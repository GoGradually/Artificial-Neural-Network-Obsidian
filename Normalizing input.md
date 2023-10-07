![[Pasted image 20231002115428.png]]
Input 정규화(normalizing input)는 머신 러닝 및 딥 러닝에서 주어진 데이터의 입력을 특정한 방식으로 변환하는 과정을 의미합니다. 입력 데이터를 정규화하는 목적은 다음과 같습니다:

1. 스케일 일치: 입력 데이터의 스케일(scale)을 일치시키는 것입니다. 스케일이 일치하지 않는 경우, 학습 과정에서 각 특성(feature)의 가중치에 차이가 크게 나타날 수 있으며, 이로 인해 모델의 수렴이 느려지거나 불안정해질 수 있습니다.
    
2. 수렴 가속화: 정규화된 입력 데이터는 모델의 수렴을 가속화할 수 있습니다. 특히 경사 하강법(gradient descent)과 같은 최적화 알고리즘에서 입력 데이터가 정규화되면 더 빠르게 수렴할 수 있습니다.
    
3. 이상치 처리: 정규화는 이상치(outlier)에 대한 모델의 민감성을 줄일 수 있습니다. 이상치는 대부분 입력 데이터의 분포에서 큰 차이를 보이므로, 정규화를 통해 이러한 이상치의 영향을 줄일 수 있습니다.
    
4. 모델의 안정성 향상: 입력 데이터의 정규화는 모델의 안정성을 향상시킬 수 있습니다. 이는 모델의 학습과 일반화 능력에 긍정적인 영향을 미칩니다.
    

주요한 정규화 기법 중 하나는 평균을 0으로, 표준편차를 1로 만드는 Z-정규화(Z-score normalization)입니다. 이 외에도 최소-최대 스케일링(Min-Max scaling), 로버스트 스케일링(Robust scaling) 등 다양한 정규화 기법이 있습니다. 어떤 정규화 기법을 사용할지는 데이터의 특성과 모델의 요구사항에 따라 다를 수 있습니다.