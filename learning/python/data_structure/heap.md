# Heap

构建 `最小堆` (如果要构建最大堆，对入堆元素取负即可)，堆顶为最小值

### 0. 创建

```python
import heapq
heapq.heapify(heap) # 构建/调整一个堆
```

### 1. 入堆并重排

```python
heapq.heappush(heap, item) # 向堆添加元素，重新排序
```

### 2. 出堆并重排

```python
heapq.heappop(heap) # 返回堆顶元素（最小值），重新排序
```

### 3. 结果

```python
heapq.nlargest(n, iterable, key) # 返回最大的n个数的列表
heapq.nsmallest(n, iterable, key) # 返回最小的n个数的列表
```

### 4. 其他

```python
heapq.merge(*iterables) # 合并多个有序列表，并返回有序列表的迭代器(即需要手动list())
```
