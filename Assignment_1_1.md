## 使用Pandas处理Excel文件

*跑完一堆cases，能不能一键处理数据比较？能不能把需要的内容自动画图？*

**本节任务：**

- 使用pandas.read_csv()读取某一个文件夹中的一个文件，会自动生成一个DataFrame。（其实这相当于把数据都导入了内存，想象为内存中有一个数据表格，DataFrame是pandas定义的一种数据结构）；
- 选择一个文件夹，把其中的两个数据文件组合成一个DataFrame（DataFrame有个方法为append）；
- 把上一条的任务做成一个函数（名为Read_Data），函数输入是文件夹的目录，输出是一个处理好的DataFrame（考虑能够处理：1.文件夹中的文件个数未知，2.文件夹中有子文件夹，3.文件夹中有其他格式的文件，等等）；
- 使用上一条的函数，对每个文件夹分别生成一个DataFrame，即生成两个DataFrame；

```
import pandas as pd
def Read_Data(path)
    # write your code here
  
## define the paths of two data folder
Path1 = r'' # 在string前面加r，表示不对string中的内容进行转义
Path2 = r''

## get two DataFrames
DF1 = Read_Data(Path1)
DF2 = Read_Data(Path2)

## print the descriptions of this two DataFrames
print("DF1's description:")
DF1.describe()
print("DF2's description:")
DF2.describe()

```
