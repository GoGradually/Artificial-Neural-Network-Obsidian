선형 레이어를 빠르게 만들기 위한 모듈 생성 메소드

~~~python
import torch
class shallow_newral_network(nn.Bodule):
	def __init__(self, num_input_features, num_hiddens):
		super().__init__()
		self.num_input_features = num_input_features
		self.num_hiddens = num_hiddens
		#linear 이용
		self.linear1 = nn.Linear(num_input_features, num_hiddens)
		self.linear2 = nn.Linear(num_hiddens, 1)
		
		self.tanh = torch.nn.Tanh()
		self.sigmoid = torch.nn.Sigmoid()		
	
	def forward(self, x):
		z1 = self.linear1(x)
		a1 = self.tanh(z1)
		z2 = self.linear2(a1)
		a2 = self.sigmoid(z2)
		return a2
~~~