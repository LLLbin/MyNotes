# PriorityQueue

基于优先级的队列的实现，列中的元素会根据设定的优先级进行排序，优先级最低的元素（数值最小）先被取出。

### 0. 创建

```python
from queue import PriorityQueue
pq = PriorityQueue()
```

### 1. 入队并重排

```python
# 向队列中添加元素，(priority, item)
pq.put((2, 'level two'))
pq.put((1, 'level one'))
pq.put((3, 'level three'))
```

### 2. 出队并重排

```python
# 从队列删除并返回priority最低的元素，(priority, item)
pq.get()  
```

### 3. 其他

```python
pq.qsize()   # 返回队列中的项数
pq.empty()   # 如果队列为空
pq.full()    # 如果队列已满
```
