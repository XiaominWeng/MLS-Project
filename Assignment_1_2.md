## 使用Pandas处理Excel文件

*跑完一堆cases，能不能一键处理数据比较？能不能把需要的内容自动画图？对于重复性工作，写个脚本一键搞定考虑一下？*

**本节任务1：**
*先将Assignment_1_2_file中的两个文件夹下载，并放在某个目录下*
- 使用pandas.read_csv()读取某一个文件夹中的**某一个csv文件**，会自动生成一个DataFrame。（其实这相当于把数据都导入了内存，想象为内存中有一个数据表格，DataFrame是pandas定义的一种数据结构）；
- 给定**文件夹路径**（./Assgin_1_2_folder1），把其中的所有csv数据文件读取并组合成一个DataFrame（考虑如何使用os；DataFrame有个方法为append，不过在使用之后注意观察一下生成的DataFrame有什么问题？有没有什么参数可以解决？）；
- 把上一条的任务做成一个函数（名为Read_Data），函数输入是文件夹的目录，输出是一个处理好的DataFrame（考虑能够处理：1.文件夹中的文件个数未知，2.文件夹中有子文件夹，3.文件夹中有其他格式的文件，等等）；
- 使用上一条的函数，对每个文件夹分别生成一个DataFrame，即生成两个DataFrame；

```
import pandas as pd
def Read_Data(path)
    # write your code here, return a DataFrame
  
## define the paths of two data folder
Path1 = r'' # 在string前面加r，表示不对string中的内容进行转义
Path2 = r''

## get two DataFrames for two different folder
DF1 = Read_Data(Path1)
DF2 = Read_Data(Path2)

## print the descriptions of this two DataFrames
print("DF1's description:")
DF1.describe()
print("DF2's description:")
DF2.describe()

```

**本节任务2：**
*使用任务1中得到的DF1和DF2进行数据比较：*
- 求DF1和DF2中**KPIs**的**绝对值绝对误差**，结果存在一个新的DataFrame中，命名为AbsError；
- 假设DF1为baseline，计算**绝对值相对误差**，结果存在一个新的DataFrame中，命名为RelError；
- 
