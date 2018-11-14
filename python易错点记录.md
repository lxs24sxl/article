# python易错点记录


#### 1.读取文件报=>UnicodeDecodeError: 'gbk' codec can't decode byte 0x99 in position 1311: illegal multibyte sequence  

解决方法1:
```
file_object= open('alice.log','r', encoding='UTF-8')
```
解决方法2:
```
file_object= open('alice.log','rb')
```