# String

### 0. 创建

```python
str = 'Hello, World!'
str = "Hello, World!"
str = "A" * 5 # "AAAAA"

str = "Hello, %s!" % "World"
str = "Hello, {}!".format("World")
str = f"Hello, {world}!" # world是个变量, 推荐这个写法
```

### 1. 查找和替换

```python
str.find(sub[, start[, end]])  # 返回子串 sub 在字符串中的最低索引。如果找不到，则返回 -1。
str.rfind(sub[, start[, end]]) # 返回子串 sub 在字符串中的最高索引。如果找不到，则返回 -1。
str.replace(old, new[, count]) # 返回字符串的副本，其中 old 的所有实例都被 new 替换。可选参数 count 限制替换次数。
str.count(sub, [start], [end]) # 返回子字符串 sub 在 [start, end] 范围内非重叠出现的次数。
```

### 2. 大小写转换

```python
str.lower() # 返回字符串的小写副本。
str.upper() # 返回字符串的大写副本。
str.capitalize() # 返回字符串的副本，其中首字母大写，其余小写。
str.title() # 返回字符串的副本，其中每个单词的首字母大写，其余小写。
str.swapcase() # 返回字符串的副本，其中大写字母转换为小写，小写字母转换为大写。
```

### 3. 去除空白

```python
str.strip([chars]) # 返回字符串的副本，其中开头和结尾的字符都已删除。可选参数 chars 指定要删除的字符集。
str.lstrip([chars]) # 删除字符串开头的字符。
str.rstrip([chars]) # 删除字符串结尾的字符。
```

### 4. 分割和连接

```python
str.split([sep[, maxsplit]]) # 使用可选的分隔符 sep 将字符串分割成部分。可选参数 maxsplit 限制分割次数。
str.rsplit([sep[, maxsplit]]) # 与 split() 类似，但从右到左分割。
str.splitlines([keepends]) # 将字符串按行分割。
str.join(iterable) # 使用字符串作为分隔符，将可迭代的元素连接成一个新字符串。
```

### 5. 格式化

```python
str.format(*args, **kwargs) # 使用位置和关键字参数格式化字符串。
str.format_map(mapping) # 使用字典来格式化字符串。
```

### 6. 判断属性

```python
str.startswith(prefix[, start[, end]]) # 检查字符串是否以指定前缀开头。
str.endswith(suffix[, start[, end]]) # 检查字符串是否以指定后缀结尾。

str.isalpha() # 检查字符串是否只包含字母。
str.isdigit() # 检查字符串是否只包含数字。
str.isalnum() # 检查字符串是否只包含字母 + 数字。
str.isspace() # 检查字符串是否只包含空白。
str.islower() # 检查字符串中的字符是否都是小写。
str.isupper() # 检查字符串中的字符是否都是大写。
```
