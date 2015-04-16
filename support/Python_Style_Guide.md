i的
n代码编写格式规范

## 写在前面
这个规范翻译自[The Pocoo Style Guide](http://www.pocoo.org/internal/styleguide/)，Pocoo style规范来自Python 官方的[PEP8规范](http://www.python.org/dev/peps/pep-0008)，改掉了一点东西，增加了一点东西。但是作为规范还是很好用，写出来的代码可读性也很强。

## 正文

### 基本布局
**缩进**
4个空格，不用Tab。
    
**行长度**
尽量保证79个字符串，有必要的话可以加到84个。多使用 break， continue，和 return来避免很深的嵌套。

**太长怎么办**
可以使用反斜杠「\」来切割一行代码，如：

在适当的位置放入斜杠，然后起头空四个空格，让「.」来做下一行开头

~~~python
this_is_a_very_long(function_call, 'with many parameters') \
    .that_returns_an_object_with_an_attribute

MyModel.query.filter(MyModel.scalar > 120) \
             .order_by(MyModel.name.desc()) \
             .limit(10)
~~~
如果代码中有括号，下一行开头与括号对齐

~~~python
this_is_a_very_long(function_call, 'with many parameters',
                    23, 42, 'and even more')
~~~
列表中有大量元素，在建立后，立刻换行，用括号做头尾

~~~python
items = [
    'this is the first', 'set of items', 'with more items',
    'to come in this line', 'like this'
]
~~~

**如何使用空行**
最高层的函数使用两个空行，其余都是一行。

### 公式和声明
**基本原则**

- 一元操作不用留空格，例如：exp = -1.05
- 二元操作中留空格，例如：value = (item\_value / item\_count) * offset / exp

**变量放在前**

~~~python
if method == 'md5':
    pass
~~~

**比较**

- 两值比较尽量不使用“==”和“!=”
- 不要使用“is”和“is not”
- 不要和True、False进行比较，例如：foo == False，不建议使用，可以写成 not foo

**否定的使用**

~~~python
foo not in bar <<<good
not foo in bar <<<bad
~~~

### 命名规则

- 类命名使用单个词首字母大写，例如CamelCase，缩写的名称全部大写，例如：HTTPWriter，而不是：HttpWriter
- 变量名：lowercase\_with\_underscores
- 方法和函数名：lowercase\_with_underscores
- 常量：UPPERCASE\_WITH_UNDERSCORES
- 编译的正则表达式：name_re

Protected members are prefixed with a single underscore. Double underscores are reserved for mixin classes.

On classes with keywords, trailing underscores are appended. Clashes with builtins are allowed and must not be resolved by appending an underline to the variable name. If the function needs to access a shadowed builtin, rebind the builtin to a different name instead.

函数和方法命名：

- 类方法：cls 作为第一个参数
- 实例方法：self 作为第一个参数
- Lambdas for properties may have the first parameter replaced with x, as in display_name = property(lambda x: x.real_name or x.username).

### 字符串

尽可能短，最好是一行写完，如果分多行写完，最后的引号另起一行。

**Module header：**
样例：

```python
# -*- coding: utf-8 -*-
"""
    package.module
    ~~~~~~~~~~~~~~

    A brief description goes here.

    :copyright: (c) YEAR by AUTHOR.
    :license: LICENSE_NAME, see LICENSE_FILE for more details.
"""
```

### 评论
评论的格式和字符串差不多，如果评论用在属性前，在#后加一个冒号。
示例：

~~~python
class User(object):
    #: the name of the user as unicode string
    name = Column(String)
    #: the sha1 hash of the password + inline salt
    pw_hash = Column(String)
~~~
