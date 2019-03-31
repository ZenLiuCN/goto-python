# goto-python

介绍基本的python环境安装和入门资源

## windows环境搭建

安装前准备: 
1. 下载通用代码编辑 推荐[notepad2](https://github.com/ProgerXP/Notepad2e) 或者 [notepad3](https://github.com/rizonesoft/Notepad3)

**注**: 命令均按照windows cmd 的命令方式介绍

### 清华镜像下载 miniconda安装

下载地址

[清华miniconda镜像清单](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/)

[最新windows版本](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Windows-x86_64.exe)

### 配置conda数据源镜像提高库安装速度

创建 `c:\Users\%用户名%\.condarc` 文本文件
写入下面的配置

*注*: windows 资源管理器不允许创建 `.`开头的文件,可以先保存为`condarc.txt` 然后命令行中进行重命名`ren condarc.txt ren .condarc`
```
channels:
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/menpo/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
# - defaults
show_channel_urls: true
auto_update_conda: false
ssl_verify: False
```
### 安装快速学习环境

`开始菜单`中启动 `Anaconda Prompt`,进入命令行,运行`conda`包管理命令进行包安装

这里安装jupyter 用于编写学习脚本和测试

`conda install jupyter jupyter_contrib_nbextensions jupyter_nbextensions_configurator nb_conda_kernels`

安装jupyter扩展

`jupyter contrib nbextension install`

安装完成之后,用changedirectory `cd` 命令 切换到要保存练习脚本的目录 比如`d:\python`
```bat
;切换目录
d:\
cd d:\python
;启动jupyter notebook
jupyter notebook
```
启动后命令行提示类似下面所示
```
[I 12:00:11.139 NotebookApp] [nb_conda_kernels] enabled, 1 kernels found
[I 12:00:17.396 NotebookApp] [jupyter_nbextensions_configurator] enabled 0.4.1
[I 12:00:17.396 NotebookApp] Serving notebooks from local directory: D:\Dev\eggs
[I 12:00:17.396 NotebookApp] The Jupyter Notebook is running at:
[I 12:00:17.396 NotebookApp] http://localhost:8888/?token=d8ca32005094022af44759e1404cbd4afd75921d6e6f0c62
[I 12:00:17.396 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 12:00:17.564 NotebookApp]

    To access the notebook, open this file in a browser:
        file:///C://Users/Administrator/AppData/Roaming/jupyter/runtime/nbserver-1624-open.html
    Or copy and paste one of these URLs:
        http://localhost:8888/?token=d8ca32005094022af44759e1404cbd4afd75921d6e6f0c62
```        
访问地址`http://localhost:8888/?token=d8ca32005094022af44759e1404cbd4afd75921d6e6f0c62`即可进入jupyter编辑环境

## jupyter 基本用法介绍

1. 参阅官方项目[站点](https://jupyter.org/)
2. 比较精要的[入门说明](https://segmentfault.com/a/1190000013014274?utm_source=tag-newest)

## 开始了解python

### 概要
1. python(指python编程语言)是一种强格式的脚本语言,即 python 代码有`强格式要求`,python是在`执行时进行解释运行`
2. python(指python编程环境)是目前较好的非计算机专业学习和进行数据处理分析的语言工具.**一般我们不随意断言**. 因为python有目前较为全面的工具包(各种由其他人员提供的预先编写好的脚本片段)涵盖数学计算\生物分析\网络操作服务...等各个方面,并且基础入门相对容易.需要**注意**的是 不建议用python作为工业信息系统生产开发.
3. 文件 python 的文件扩展名`.py`.在unix\*系统下 一般由`#!/bin/python`来定义解析器,文件可以没有扩展名.
4. 需要注意前面环境搭建介绍使用的jupyter 生成的文件是`json`格式,而非标准python脚本
5. python有 2.x版本和3.x版本区别,建议直接学习3.x版本
### 入门路径
1. python是强格式要求的语言,python没有采用括弧`{`来作为代码块区分,而是采用缩进的方式进行区分,所以请注意代码中的空格缩进.
2. 第一阶段: 建议学习了解基本语法 `数据类型` `变量` `运算符` `条件语句` `循环语句`等(不建议本阶段去了解对象部分),并在jupyter进行相应练习.依照基础的不同预计消耗时间在30分钟-4小时之间
3. 第二阶段: 在了解语法基础上,进一步学习 `模块` `内置函数` `异常处理` `文件操作` 等. 该部分学习完成应当达成了解python的基础脚本编写过程和多脚本文件组织方式,在此基础上应当可以通过内置包进行诸如: 文本文件处理,系统控制等基础操作.
4. 第三阶段: 按照学习目标的不同,选择 `学习工具库`进而解决实际问题 或者`进一步学习python面向对象`深入了解python
5. 无止境阶段: 按阶段4的选择目标,本阶段需要同步进行上阶段两个方向.同时按个人目标不同可以学习了解C/C++,网络通讯或者数学,统计学等各种相关知识.

### 部分工具库
1. numpy库: 已知的最方便的高阶数学处理库
2. matplotlib库: 方便的绘图工具包,常用于图表绘制
3. opencv库: 图像处理和分析工具包,需要先了解1和2,并对基本的数字影像有一定了解
4. tenserflow库: google家的机器学习平台(需要有git操作知识,深度学习基础)
5. 其他: python各种工具库多不胜数,可以通过网络搜索或[包索引](https://pypi.org/)去检索完成目标需要的库进行学习

### 资源
1. 基础了解[菜鸟教程](http://www.runoob.com/python/python-tutorial.html) 或者[廖雪峰](https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)
2. 官方站点[python](https://www.python.org/)
