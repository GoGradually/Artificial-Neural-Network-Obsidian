~~~python
import matplotlib.pyplot as plt
import numpy as np
def imshow(img):
	npimg = img.numpy()
	plt.imshow(np.transpose(npimg, (1, 2, 0)))
	plt.show()

dataiter = iter(test_loader)
images, labels = dataiter.next()

imshow(torchvision.utils.make_grid(images, nrow = batch_size))
print('GroundTruth')
print(" " + ' '.join('%3s' % label.item() for label in labels))

outputs = model(images)
_, predicted = torch.max(outputs, 1)
print("Prediction")
print(" " + ' '.join('%3s' % label.item() for label in predicted))

n_predict = 0
n_correct = 0

for data in test_loader:
	inputs, labels = data
	outputs = model(inputs)
	_, predicted = torch.max(outputs, 1)
	
	n_predict += len(predicted)
	n_correct += (labels == predicted).sum()

print(f"{n_correct}/{n_predict}")
print(f"Accuracy: {n_correct/n_predict : .3f}")
~~~