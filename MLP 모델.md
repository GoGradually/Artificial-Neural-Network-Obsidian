Multilayer perceptron

~~~python
from torch import nn
class MLP_h(nn.Module):
	def __init__(self, hidden_units = [512, 256, 128]):
		super().__init__()
		
		self.in_dim = 28*28 #MNIST
		self.out_dim = 10
		
		self.l_layers = nn.ModuleList()
		self.l_layers.append(nn.Linear(self.in_dim, hidden_units[0]))
		for i in range(len(hidden_units) - 1):
			self.l_layers.append(nn.Linear(hidden_units[i], hidden_units[i+1]))
		self.l_layers.append(nn.Linear(hidden_units[-1], self.out_dim))
		
		self.relu = nn.ReLU()
		self.log_softmax = nn.LogSoftmax()
	
	def forward(self, x):
		a = x.view(-1, self.in_dim)
		for l in range(len(self.l_layers)):
			z = self.l_layers[l](a)
			if l == len(self.l_layers) - 1:
				logit = z
			else:
				a = self.relu(z)
		
		return logit
~~~


[[logit]]