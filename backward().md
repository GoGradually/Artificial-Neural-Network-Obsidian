~~~python
cost = 0.0
cost.backward()
~~~

cost 함수에 backward() 계산한 뒤의 변수값 추가
그 뒤 [[optimizer.step()]] 사용