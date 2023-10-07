~~~python
import torch.optim as optim
model = MLP_h([]) # 리스트 크기 지정하기
criterion = nn.CrossEntropyLoss()
optimizer = optim.SGD(model.parameters(), lr = 0.01)

for epoch in range(10):
	running_loss = 0.0
	for i, data in enumerate(train_loader, 0):
		#get the inputs; data is a list of [inputs, labels]
		inputs, labels = data
		
		#zero the parameter gradients
		optimizer.zero_grad()
		
		#forward + backward + optimize
		outputs = model(inputs)
		loss = criterion(outputs, labels)
		loss.backward()
		optimizer.step()
		
		#printf statistics
		running_loss += loss.item()
		if(i + 1) % 2000 == 0:
			print('[%d, %5d] loss: %.3f' %
				(epoch+1, i+1, running_loss/2000))
			running_loss = 0.0
			
print('Finished Training')
~~~