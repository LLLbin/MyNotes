# Dict

### 0. 创建

```python
dict = {}
dict = {'a': 1, 'b': 2, 'c': 3}
dict = dict([('a', 1), ('b', 2), ('c', 3)])
dict = dict(a=1, b=2, c=3)
dict = {x: x**2 for x in (2, 4, 6)} # {2: 4, 4: 16, 6: 36}
dict = dict.fromkeys(keys, value) # {'a': 0, 'b': 0, 'c': 0}
dict = dict(zip(keys, values)) # {'a': 1, 'b': 2, 'c': 3}
```

### 1. 索引

```python
dict['keyname'] # 根据key返回value，不存在则报错
dict.get(key[, default]) # 返回给定键的值。如果键不在字典中，则返回可选的默认值（默认为None）。
dict.setdefault(key[, default]) # 如果键在字典中，则返回其值。如果不在，则插入键和默认值（如果提供）并返回默认值。
```

### 2. 添加

```python
dict['new_keyname'] = new_value # 如果key不在，则新建pair；否则更新pair。
dict.update([other]) # 使用一个字典项更新字典。
```

### 3. 删除

```python
dict.pop(key[, default]) # 删除并返回特定键的值。如果键不在字典中，则返回可选的默认值，否则引发异常。
dict.popitem() # 删除并返回一对键和值。如果字典为空，则引发异常。
dict.clear() # 删除字典中的所有项。
```

### 4. 排序

```python
# 按照字典的值进行排序
d1 = dict(sorted(d.items(), key=lambda x: x[1]))
# 按照字典的键进行排序
d2 = dict(sorted(d.items(), key=lambda x: x[0]))
```

### 5. 拷贝

```python
dict.copy() # 返回字典的浅拷贝。
dict.deepcopy() # 返回字典的深拷贝。
```

### 6. 视图对象

```python
dict.keys() # 返回字典中的键的视图对象。
dict.values() # 返回字典中的值的视图对象。
dict.items() # 返回字典项的视图对象。
```

### 7. 其他

```python
len(dict) # 返回字典中的项数。

# 找最大值最小值，多级排序
data = [{"name": "Alice", "score": 38}, 
        {"name": "Bob", "score": 38}, 
        {"name": "Cathy", "score": 45},
        {"name": "Dave", "score": 45}]

highest_score = max(data, key=lambda x: (x['score'], x['name'])) # {'name': 'Dave', 'score': 45}
lowest_score = min(data, key=lambda x: (x['score'], x['name'])) # {'name': 'Alice', 'score': 38}
```

# Defaultdict

defaultdict() : 带默认值的字典，访问不存在的键时，直接实例化一个默认值，不会得到 KeyError 异常

```python
from collections import defaultdict

dd = defaultdict(None)
dd = defaultdict(int)
dd = defaultdict(list)
```

# Counter

Counter() : 一个计数器工具，提供快速和方便的计数。key=elements，valuetimes

```python
from collections import Counter

counter.elements() # 返回一个迭代器，其中每个元素将重复出现计数值所指定次。元素返回的顺序是按照元素在原本序列中首次出现的顺序
counter.most_common([n]) # 返回一个列表，其中包含n个出现次数最高的元素及出现次数，按常见程度由高到低排序
counter.update(counter) # 将两个Counter相加，a.update(b)，a中计数增加相应的个数
counter.subtract(counter) # 将两个Counter相减，a.sbutract(b)，a中计数减少相应的个数

# 找到所有计数值为最大的元素
max_count = max(counter.values())
max_elements = [key for key, count in counter.items() if count == max_count]
```
