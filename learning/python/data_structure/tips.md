# Tips

```python
# 变量作用域管理
global -> 全局
nonlocal -> 内嵌函数 (helper)

# 字符格式化
"{} {}".format("hello", "world") # 默认
"{0} {1}".format("hello", "world") # 带位置
"{hello} {world}".format(hello="hello", world"world") # 带参数
"{:.2f}".format(3.14159) # 数字格式化 -> {:[+|-][填充字符][<^>][宽度](b|d|o|x|#x|#X)}

# 格式化输出
print(f"My name is {name} and I am {age} years old")
print("My name is {} and I am {} years old".format(name, age))
print("My name is %s and I am %d years old" % (name, age))
print("My name is " + str(name) + " and I am " + str(age) + " years old") # 最low
print(*objects, sep=' ', end='\n') # 可以设置seq和end

# 数值运算
float('inf') & float('-inf') # 最大值和最小值
round(x) # 四舍五入
x // y # 向下取整
(x + y - 1) // y # 向上取整
pow(x, y, [z]) # 求幂函数x^y，运算完毕可以顺带对z取模；大数取模问题可以直接AC
divmod() # 函数把除数和余数运算结果结合起来，返回一个包含商和余数的元组(a // b, a % b)

# 负数处理
(-3)//2 = -2 # 会往下取整
int((-3)/2) = -1 # int会往0取整

# 0和1的转换
flag =  1
flag ^= 1        # 使用异或
flag =  1 - flag # 使用减法

# 类型判断
isinstance(obj, type) # 判断类型
cmp(x, y) # 比较2个对象，x<y:1, x=y:0, x>y:1
all(iterable)/any(iterable) # 迭代与操作/迭代或操作（0、1、None均等价于False)

# functools
map(function, iterable...) # 映射函数
squares = map(lambda x: x**2, numbers) # 求平方

filter(function, iterable) # 过滤函数
evens = filter(lambda x: x % 2 == 0, numbers) # 求偶数

reduce(function, iterable, [initializer]) # 累积函数
product = reduce(lambda x, y: x * y, numbers) # 求乘积

@lru_cache(maxsize=None, typed=False) # LRU缓存，在递归和DP中取maxsize=None用作记忆法进行剪枝。

# itertools
accumulate(iterable, [func]) # 前缀和
# accumulate([1,2,3,4,5]) --> 1 3 6 10 15

product # 全排列，笛卡尔积
# product('ABCD, 2') --> AA AB AC AD BA BB BC BD CA CB CC CD DA DB DC DD

permutations # 排列，连续返回由 iterable 元素生成长度为r的排列
# permutations('ABCD, 2') --> AB AC AD BA BC BD CA CB CD DA DB DC

combinations # 组合，返回由输入iterable中元素组成长度为r的子序列
# combinations('ABCD', 2) --> AB AC AD BC BD CD

groupby(iterable, [key]) # 迭代器中相邻的重复元素挑出来放在一起
# for i, v in itertools.groupby('AABBC')
#     print(i, list(v)) --> A ['A', 'A'] B ['B', 'B'] C ['C']

# 类型转换
int(x, base=10))/float()/str() # 转整数(可自定义进制)/转浮点数/转字符串
bin()/oct()/hex() # 10进制转二进制(返回0b开头的字符串)/10进制转八进制(返回0开头的字符串)/10进制转十六进制(返回0x开头的字符串)
ord()/chr() # 字符转ASCII或ASCII转字符
complex(real, imag) # 创建一个复数，不过现在可以直接通过语法糖创建，eg：1+2j
eval(expression, [globals, locals]) # 执行一个字符串表达式，并返回表达式的值，eg：eval('pow(2, 2)')= 4

# 迭代相关
range(start=0, stop, step=1]) # 返回一个可迭代对象，常用于for循环
enumerate() # 将一个可遍历的数据对象组合为一个索引序列，eg:for i, v in enumerate(list_a):
zip(iterable, ...) # 将对象中对应的元素打包成一个个元组，常用于并联取值
map(function, iterable...) # 映射函数

# 哈希
id(obj) # 返回对象的唯一标识符，比hash()更鲁棒更快且可以对list、def等对象求id
hash(obj) # 返回哈希码，常用于对象比较或将其转化为唯一的索引

# TLE敏感操作
1. 使用 `x in obj` 取代 `obj.find(x)`
2. 使用 `list.reverse()` 取代 `list[::-1]`
3. 对list进行扩增优先使用 `for _ in range(j): li.append(x)`
4. 对list进行删除优先使用 `if x in s: s.remove(x)`
```
