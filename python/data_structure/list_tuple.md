# List & Tuple

### 0. 创建

- 一维

```py
list = []
list = [1, 2, 3, 4, 5]
list = list((1, 2, 3, 4, 5))
list = [0] * 5 # [0, 0, 0, 0, 0]
list = [i for i in range(5)] # [0, 1, 2, 3, 4]
list = [int(n) for n in str(num)] # 切分num成一个列表 123 -> [1, 2, 3]
```



- 二维

```py
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
matrix = [[0 for _ in range(3)] for _ in range(3)] # 创建3x3全0矩阵
matrix = [[0] * 3 for _ in range(3)] # 创建3x3全0矩阵
# 取矩阵的列
for col in zip(*grid):
	print(list(col))
```





### 1. 添加

```python
list.append(x) # 将元素 x 添加到列表的末尾。
list.extend(iterable) # 扩展列表，将一个可迭代的元素（如另一个列表）的所有元素添加到列表的末尾。
list.insert(i, x) # 在给定位置 i 插入元素 x。
```

### 2. 删除

```python
list.remove(x) # 删除列表中第一个值为 x 的元素。
list.pop([i]) # 删除给定位置的元素并返回它。如果没有指定索引，则删除并返回最后一个元素。
list.clear() # 移除列表中的所有元素。
```

### 3. 查找

```python
list.index(x[, start[, end]]) # 返回列表中第一个值为 x 的元素的索引。可以指定可选的 start 和 end.
list.index(max(list)) # 返回列表最大值得下标
```

### 4. 排序

```python
list.sort(key=None, reverse=False) # 对列表中的元素进行排序。可以通过 key 和 reverse 参数自定义排序。
list.sort(key=lambda x:x[0]) # 二维list按某一列的值排序

list.sort(key=len) # 按长度排序
list.sort(key=str.lower) # 忽略大小写排序
list.sort(key=lambda x: x[0]) # 按第一个元素排序

from functools import cmp_to_key
def helper_func(item1, item2):
    if item1 < item2: return -1
    elif item1 > item2: return 1
    else: return 0
list.sort(key=cmp_to_key(helper_func))
```

### 5. 翻转

```python
list[::-1] # 反转列表中的元素， 返回新list
list.reverse() # 原地反转列表中的元素。

# 反向遍历列表
for item in reversed(my_list)
for item in my_list[::-1]
for index in range(len(my_list) - 1, -1, -1)
```

### 6. 计数

```python
list.count(x) # 返回列表中 x 出现的次数。
```

### 7. 拷贝

```python
list[:] # 返回列表的浅拷贝。
list.copy() # 返回列表的浅拷贝。
list.deepcopy()  # 返回列表的深拷贝。
```

### 8. 其他

```python
len(list) # 返回列表的长度。
max(list) # 返回列表中的最大值。
min(list) # 返回列表中的最小值。
sum(list) # 返回列表中所有元素的和。
```
