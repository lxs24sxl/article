# python中OrderedDict的使用

- Python标准库是一组模块,模块collections有一个OrderedDict子类，可以记录键-值对的添加顺序，实现了对字典对象中元素的排序。

- python中的字典是无序的，因为它是按照hash来存储的。

- 兼具列表和字典的也主要优点(在将信息关联起来的同时保留原来的顺序)

```python
print("Regular dictionary")
d1={}
d1['a']='A'
d1['b']='B'
d1['d']='d'
d1['c']='C'

d2={}
d2['b']='B'
d2['a']='A'
d2['d']='d'
d2['c']='C'

print(d1==d2)

from collections import OrderedDict

favorite_languages1 = OrderedDict()

favorite_languages1['jen'] = 'Python'
favorite_languages1['sarah'] = 'c'
favorite_languages1['edward'] = 'ruby'
favorite_languages1['phil'] = 'python'

favorite_languages1 = OrderedDict()

favorite_languages2['sarah'] = 'c'
favorite_languages2['jen'] = 'Python'
favorite_languages2['edward'] = 'ruby'
favorite_languages2['phil'] = 'python'

print(favorite_languages2==favorite_languages1)
```

输出的结果为:
```s
Regular dictionary:
True

OrderedDict:
False
```

#### 结论
OrderedDict对象的字典对象，如果其顺序不同那么Python也会把他们当做是两个不同的对象



