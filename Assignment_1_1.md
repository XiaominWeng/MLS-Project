## 使用Python如何操纵系统文件以及文件夹

*如何使用Python进行文件及文件夹的访问，增删，修改等操作*

**os**是Python中的包，可以对操作系统(Operation System)进行信息读取或操作，而且不受当前操作系统的限制。
可以使用*import os*导入并使用。

**本节任务**
1. 使用**os**对系统文件夹进行操作
1. 使用Python操作，读写文本文件


### 简单列举一些os包的应用：
- os.name # 显示当前操作系统
```
>>> os.name
'nt'                  #这表示Windows
>>> os.name
'posix'             #这表示Linux
```
- os.getcwd() # 获取当前python脚本工作路径
```
>>> os.getcwd() # 自己试试会得到什么路径
```
- os.listdir(*path*) # 获取*path*路径下所有的**文件夹和文件**的名字，返回一个list
```
>>> os.listdir() # 不加参数返回当前路径下的内容
['.idea',
 '1. Two Sum.py',
 '2. Add Two Numbers.py',
 '3. Longest Un-repeated Substring.py']
```
- os.mkdir(*path*) # 新建一个文件夹
```
>>> os.mkdir('./Sunday') # 在当前路径下新建一个名为Sunday文件夹('.'表示当前文件夹)
>>> os.mkdir('./Morning/Love/Sunday') # 试试看发生了什么
```
- os.makedirs(*path*) # 新建一个文件夹
```
>>> os.makedirs('./Morning/Love/Sunday') # mkdir只能在已有路径下创建文件夹，makedirs则可以创建多层级的路径
```
- os.rmdir(*path*) # 删除一个文件夹
```
>>> os.rmdir('./Sunday') # 删除之前生成的一个文件夹，88~
```

- os.path # 这是os中一个与路径名相关的模块，有一些常用的关于路径名的操作命令，注意下面列出的没有对文件夹做出操作，实际是否有这个路径与否不影响这些函数的使用
```
>>> os.path.abspath('./Morning') # 返回相对路径的绝对路径
>>> os.path.dirname('./Morning/Love/Sunday') # 返回路径的父路径
>>> os.path.isdir('./Morning/Love/Sunday') # 判断是否是一个文件夹
>>> os.path.isfile('./Morning/DoNotLove/Sunday') # 判断是否是一个文件
>>> os.path.split('./Morning/Love/Sunday') # 将目录分割为父路径和最后一个文件夹名，对于文件也适用
>>> os.path.join('Just', 'Try', 'It') # 将多个字符串组合成路径名
```

### Python中对文件的简单操作
和大部分其他语言类似，Python对文件的读写也基本分为：新建/打开一个文件，读取其中的内容，写入内容，关闭文件等步骤。
- 新建/打开文件
```
>>> file = open('./Morning/Love/Sunday/everday.txt', 'w') 
# 'w'表示write，如果改文件存在，则覆盖改文件，否则新建文件；file可以想象为在内存中的一个临时文件
```
- 向文件里写点什么
```
>>> file.write('What do you want to say?') # 现在打开文件everyday.txt看看，有内容么？
```
- 关闭（保存）文件
```
file.close() # 再看看该文件，就像新建的时候说的，在使用open打开文件之后，只是相当于在内存中的一个临时文件，在close文件之前都不会写入硬盘
```
这就引来了一个问题：一旦在文件打开到close之前程序停了
