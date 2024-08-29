# Set

### 0. 创建

```python
set = {1, 2, 3, 4}
set = set([1, 2, 3, 4])
set = {x for x in range(5)}

set() # 去重技巧，判断元素是否在set比在list快很多
```

### 1. 添加

```python
set.add(elem) # 将元素 elem 添加到集合中。
set.update(*others) # 使用一个或多个其他集合更新集合，相当于集合的联合。
```

### 2. 删除

```python
set.remove(elem) # 从集合中删除元素 elem。如果元素不存在，则引发 KeyError。
set.discard(elem) # 从集合中删除元素 elem（如果存在）。
set.pop() # 删除并返回集合中的任意元素。如果集合为空，则引发 KeyError。
set.clear() # 删除集合中的所有元素。
```

### 3. 数学运算

```python
set.union(*others) # 返回一个新集合，包括所有集合的元素。
set.intersection(*others) # 返回一个新集合，包括所有集合的交集元素。
set.difference(*others) # 返回一个新集合，包括与所有其他集合的差集元素。
set.symmetric_difference(other) # 返回一个新集合，包括与另一个集合的对称差集元素。
```

### 4. 比较运算

```python
set.issubset(other) # 判断集合是否是另一个集合的子集。
set.issuperset(other) # 判断集合是否是另一个集合的超集。
set.isdisjoint(other) # 判断集合与另一个集合是否有交集。
```

### 5. 拷贝

```python
set.copy() # 返回集合的浅拷贝。
set.deepcopy() # 返回集合的深拷贝。
```

### 6. 其他

```python
len(set) # 返回集合中的元素数量。
set(iterable) # 使用可迭代对象创建新集合。
```
