# Markdown

### 1. 标题 (Headers)

使用 `#` 来表示不同级别的标题。数量越多，标题级别越低。

```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
```

### 2. 强调 (Emphasis)

使用 `*` 或 `_` 表示斜体，使用 `**` 或 `__` 表示加粗。

```markdown
*斜体* 或 _斜体_
**加粗** 或 __加粗__
***加粗斜体*** 或 ___加粗斜体___
```

### 3. 列表 (Lists)

#### 无序列表 (Unordered List)

使用 `-`、`*` 或 `+` 来创建无序列表。

```markdown
- 项目1
- 项目2
  - 子项目
  - 子项目

* 项目1
* 项目2

+ 项目1
+ 项目2
```

#### 有序列表 (Ordered List)

使用数字加 `.` 创建有序列表。

```markdown
1. 项目1
2. 项目2
   1. 子项目
   2. 子项目
```

### 4. 链接 (Links)

使用 `[文本](链接)` 创建链接。

```markdown
[Google](https://www.google.com)
```

### 5. 图片 (Images)

使用 `![文本](图片链接)` 插入图片。

```markdown
![text](https://markdown-here.com/img/icon256.png)
```

### 6. 引用 (Blockquotes)

使用 `>` 表示引用。

```markdown
> 这是一个引用
>> 这是嵌套的引用
```

### 7. 代码 (Code)

#### 行内代码 (Inline Code)

使用反引号 `` ` `` 包裹行内代码。

```markdown
这是 `行内代码` 示例。
```

#### 代码块 (Code Blocks)

使用三个反引号 `` ``` `` 包裹多行代码，并可指定代码语言。

```python
def hello():
    print("Hello, World!")
```

### 8. 分割线 (Horizontal Rule)

使用 `---`、`***` 或 `___` 创建分割线。

```markdown
---
***
___
```

### 9. 表格 (Tables)

使用 `|` 分隔单元格，使用 `-` 创建表头下的分隔线。

```markdown
| table 1 | table 2 | table 3 |
|  -----  |  -----  |  -----  |
|    1    |    2    |    3    |
|    4    |    5    |    6    |
```

### 10. 任务列表 (Task Lists)

使用 `- [ ]` 创建未完成任务，使用 `- [x]` 创建已完成任务。

```markdown
- [x] 已完成任务
- [ ] 未完成任务
```

### 11. 数学公式 (Math)

Markdown 插入数学公式：

1. 行内公式

```markdown
$E = mc^2$
```

2. 行间公式

```markdown
$$
\int_0^\infty e^{-x}\,dx = 1
$$
```

### 12. 目录 (Table of Contents)

使用 `[toc]` 插入目录。

```markdown
[toc]
```

### 13. 美人鱼图 (Mermaid)

使用插入Mermaid代码来快捷加入图表。

[官网文档](https://mermaid.js.org/intro/)

[在线编辑器](https://mermaid.live/edit)
