리스트를 만들 땐 파이썬 리스트를 사용하지 않고
ModuleList를 만들어야 한다!
(파이썬 리스트는 pytorch가 추적 불가능하다.)
~~~python
self.linears = nn.ModuleList([nn.Linear(10, 10) for i in range(10)])
~~~


