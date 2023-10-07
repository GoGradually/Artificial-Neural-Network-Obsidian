레이어를 편하게 만들기 위한 클래스
모든 pytorch 내 
- autograd와 완전히 통합되어있다
- CPU/GPU 사이 변환이 자유롭고 저장과 복구가 용이하다
~~~python
import torch
from torch import nn

class MyLinear(nn.Module):
	def __init__(selc, in_features, out_features):
		super().__init__()
		# weight는 input*output 크기의 리스트
		self.weight = nn.Parameter(torch.randn(in_features, out_features))
		# bias도 output 크기의 리스트
		self.bias = nn.Parameter(torch.randn(out_features))
	def forward(self, input):
		return (input @ self.weight) + self.bias
~~~

~~~python
m = MyLinear(4, 3)
sample_input = torch.randn(4)
# call forward
m(sample_input) 
: tensor([-0.3036, -1.0413, -4.2057], grad_fn=<addBackward0>)
~~~
선형 레이어는 편하게 만들기 위한 [[Linear()]]이 존재한다.

레이어가 모여서 만들어진 모델도 모듈이다!
![[Pasted image 20231006142758.png]]