# python 作弊笔记参考——数据类型

## 字符串（str）

### 基本操作
**字符串加法**

```python
a = "zha"
b = "lie!"
c = a+b
print(c)
zhalie!
```

**打印字符串**

```python
print("%s%s"%(a,b))
zhalie!
```

**字符串格式化（推荐**）

```python
print("{0}!{1}".format(a,b))
zha!lie!
```

```python
print("{1}!{0}".format(b,a))
zha!lie!
```

```python
ao_dict = {'a':'zha', 'b':'lie!'}#ao_dict为字典
print("{a}!{b}".format(**ao_dict))
zha!lie!
print("{c}!{d}".format(c = 'zha', d = 'lie!'))
zha!lie!
```

## 列表（list）

### 定义列表

```python
ao = ['z','h','a','l','i','e','!']

print(ao[0],ao[1],ao[-2])
('z','h','e')
```

### 列表操作

**字符串操作**

```python
s = ''.join(ao)#将列表合并成字符串
print(s)
zhalie!
```
**列表反转**

```python
ao[::-1]
['!', 'e', 'i', 'l', 'a', 'h', 'z']
```

**列表追加元素**

```python
ao.append('!')
print(ao)
['z', 'h', 'a', 'l', 'i', 'e', '!', '!']
#换一种方法
ao[len(ao):] = ['!','!']
print(ao)
['z', 'h', 'a', 'l', 'i', 'e', '!', '!','!','!']
```
*拓展：list.extend(list)*

**列表中元素的个数&位置**

```python
ao.count('!')#列表中感叹号的个数
4
ao.index('!')#列表中第一个感叹号位置
6
ao[::-1].index('!')#这时候第一个感叹号在哪？猜一下
#看看猜的对不对
ao.index('z')
0
```

## 字典（dict）

### 定义字典

```python
ao = {'a':'zha','b':'lie',1:'!'}
print(ao['a'])
zha
print(ao[1])
!
```


## 元组（tuple）

>**元组是用圆括号括起来的，其中的元素之间用逗号隔开。（都是英文半角）**
>tuple是一种序列类型的数据，这点上跟list/str类似。它的特点就是其中的元素不能更改，这点上跟list不同，倒是跟str类似；它的元素又可以是任何类型的数据，这点上跟list相同，但不同于str。

>一般认为,tuple有这类特点,并且也是它使用的情景:
>
>- Tuple 比 list 操作速度快。如果您定义了一个值的常量集，并且唯一要用它做的是不断地遍历它，请使用 tuple 代替 list。
- 如果对不需要修改的数据进行 “写保护”，可以使代码更安全。使用 tuple 而不是 list 如同拥有一个隐含的 assert 语句，说明这一数据是常量。如果必须要改变这些值，则需要执行 tuple 到 list 的转换 (需要使用一个特殊的函数)。
- Tuples 可以在 dictionary 中被用做 key，但是 list 不行。实际上，事情要比这更复杂。Dictionary key 必须是不可变的。Tuple 本身是不可改变的，但是如果您有一个 list 的 tuple，那就认为是可变的了，用做 dictionary key 就是不安全的。只有字符串、整数或其它对 dictionary 安全的 tuple 才可以用作 dictionary key。
- Tuples 可以用在字符串格式化中，后面会用到。

## 集合（set）

>set拥有类似dict的特点:可以用{}花括号来定义；其中的元素没有序列,也就是是非序列类型的数据;而且,set中的元素不可重复,这就类似dict的键.

### 集合的创建

```python
ao = set("zhalie!!")
print(ao)
set(['a', '!', 'e', 'i', 'h', 'l', 'z'])#只有一个感叹号了
```

### 集合的变换&判断

```python
a = set("zha")#将字符串转为set
b = {"l","i","e","!"}#新建一个set

a == b
False

a != b
True
```
### 数学上的「集合」的用法

```python
c = {"a"}

c<a #判断c是不是a的子集
True

"a" in a #元素a是不是在集合内
True

a | b #a和b的并集
set(['a', '!', 'e', 'i', 'h', 'z', 'l'])

a & c #a和b的交集
set(['a'])

```

