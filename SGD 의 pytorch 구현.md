~~~python
num_epochs = 100
lr = 1.0
num_hiddens = 3

model = shallow_neural_network(2, num_hiddens)
optimizer = optim.SGD(model.parameters(), lr = lr)
loss_fn = nn.BCELoss() # loss function 의 형태가 Binary Cross Entropy

for epoch in range(num_epochs):
	cost = 0.0
	for batch in dataloader:
		X_batch, y_batch = batch
		y_hat = model(X_batch)
		
		loss = loss_fn(y_hat, y_batch) #y_hat 과 y사이 손실값
		optimizer.zero_grad()
		loss.backward()
		optimizer.step()
		
		cost += loss.item()
	cost = cost / len(X)
	if epoch%10 == 0:
		print(epoch, cost)
~~~