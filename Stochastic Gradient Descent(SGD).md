**Mini-Batch Gradient Descent (미니 배치 경사 하강법):**
    - 전체 학습 데이터셋을 미니 배치(mini-batch)로 나누어 각 미니 배치를 사용하여 경사를 계산하고 모델 파라미터를 업데이트합니다.
    - 미니 배치 크기를 조절하여 메모리 사용량과 연산 비용을 관리할 수 있습니다.
    - SGD보다 안정적이며 빠른 학습이 가능합니다.
    - 대부분의 딥 러닝 모델 학습에서 사용되는 경사 하강법입니다.

![[Pasted image 20230929223139.png]]
![[Pasted image 20230929223709.png]]
일반적으로 SGD라 불리는 것은 Mini-batch Gradient Descent.

같이보기
- [[진짜 Stochastic Gradient Descent]]
- [[Stochastic Gradient Descent vs. Gradient Descent]]