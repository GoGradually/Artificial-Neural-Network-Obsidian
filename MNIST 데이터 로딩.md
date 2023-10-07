~~~python
import torchvision
import torch
from torchvision import datasets, transforms
batch_size = 12
train_data = datasets.MNIST('~/Documents', train = True, download=True, transform = transforms.ToTensor())
test_data = datasets.MNIST('~/Documents', train=False, download=True, transform = transforms.ToTensor())

train_loader = torch.utils.data.DataLoader(train_data, batch_size = batch_size, shuffle = True)
test_loader = torch.utils.data.DataLoader(test_data, batch_size = batch_size)
~~~