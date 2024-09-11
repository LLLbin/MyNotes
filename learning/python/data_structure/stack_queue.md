# Stack & Queue

### 0. 创建

```python
from collections import deque
stack = deque()
queue = deque()
```

### 1. Stack

```python
# 1. 使用deque作为栈
stack.append('a')  # 压栈
stack.append('b')  # 压栈
stack.pop()        # 出栈，返回 'b'
```

### 2. Queue

```python
# 2. 使用deque作为队列
queue.append('a')  # 入队
queue.append('b')  # 入队
queue.popleft()    # 出队，返回 'a'
```

# Deque

### 0. 创建

```python
from collections import deque
dq = deque()
```

### 1. 添加

```python
deque.append(x) # 在队列右边（尾部）插入x
deque.appendleft(x) # 在队列左边（头部）插入x

deque.extend(iterable) # 将可迭代对象扩展到队列右边
deque.extendleft(iterable) # 将可迭代对象扩展到队列左边

deque.insert(i, x) # 插入元素x到指定位置x。如果位置超出范围，抛出IndexError异常
```

### 2. 删除

```python
deque.pop() # 在队列左边（尾部）出栈
deque.popleft() # 在队列右边（头部）出栈
deque.remove(x) # 删除第一个找到的元素x，没有元素抛出ValueError异常
deque.clear() # 清空队列，初始化队列长度为1
```

### 3. 查找

```python
deque.index(x) # 返回元素x在队列中的位置，没有找到抛出异常ValueError

```

### 4. 翻转

```python
deque.reverse() # 逆序
deque.rotate(n) # 将队列向右移动n个元素，如果n为负数则向左移动n个元素
```

### 5. 计数

```python
deque.count(x) # 计算队列中x元素的个数
```

### 6. 拷贝

```python
deque.copy() # 创建一个浅拷贝的队列
deque.deepcopy()  # 返回深拷贝的队列
```

### 7. 其他

```python
deque.maxlen() # 返回队列长度（不是当前的长度），为空返回None。
```
