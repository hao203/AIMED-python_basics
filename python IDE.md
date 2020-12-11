> 此教程是为湖南中医药大学智能医学社而写！转载务必注明出处！！

好马配好鞍，Python开发需要IDE，或者说高效的编辑器。[Pycharm](https://www.win7w.com/win10zhuangjiruanjian/25986.html)这种当然是程序员专用的，也是最受欢迎的，但几百兆的安装包也确实臃肿。python 自带的Idle扩展性和实用性不佳。我觉得就目前VS Code流行趋势（跨平台、高效），有一统天下的可能，而且用它Python的数据科学就会便捷很多。当然大家也可能了解Anaconda，这个数据科学的全能选手，但他实在太臃肿了，我写这文章就是为了不用他。

# 一、安装git（也可以先安装vs code）

这个不多说了，详见[安装教程](https://www.cnblogs.com/xueweisuoyong/p/11914045.html)，基本不会出问题。运行完别忘了在命令行输入git，检验一下是否安装成功。当然先安装后面其他软件也行。

# 二、安装一个好用的命令行工具

弃用Windows自带的cmd

可以在微软APP store 官方下载Windows terminal。他用起来就像在Linux一样熟悉和方便，关键是长得好看。

当然，你也可以选择Cmder等其他的命令行工具。

# 三、安装Python解释器

官方网站：[https://www.python.org/](https://www.python.org/)

有了它，你就可以运行python的代码了。安装教程请百度，几乎没难度。请安装Python 3.8版本，不要安装3.9，因为有些会报错。

测试一下命令行输入 python

# 三、安装VS Code

VS Code太好用了，自带git工具，可以免去很多git的操作命令。安装一般不存在问题，下载下来以后，要用管理员身份运行安装。

[https://code.visualstudio.com/](https://code.visualstudio.com/)

希望大家都用英文版，不要汉化。**今天我推荐的任何工具都要求用英文原版。**

**下面就是关键了。如何在Vs code中配置python的开发环境**

### 1.首先安装插件

具体的插件有python、python preview。建议安装一个比较爽的主题。你可以随意百度一下，看看有什么漂亮主题。不过我更喜欢对我眼睛好的——Tiny Light。

### 2.配置pip的国内镜像

Python之所以强大，是因为它有很多扩展包。这些包都需要一个叫pip的工具来进行管理和安装。

由于某些众所周知的原因，我们需要将pip的包安装源改为国内镜像，如果不改，安装会非常慢，甚至可能无法安装。

国内的源有：

阿里云 [https://mirrors.aliyun.com/pypi/simple/](https://mirrors.aliyun.com/pypi/simple/)

中国科技大学 [https://pypi.mirrors.ustc.edu.cn/simple/](https://pypi.mirrors.ustc.edu.cn/simple/)

豆瓣(douban) [https://pypi.douban.com/simple/](https://pypi.douban.com/simple/)

清华大学 [https://pypi.tuna.tsinghua.edu.cn/simple/](https://pypi.tuna.tsinghua.edu.cn/simple/)

中国科学技术大学 [https://pypi.mirrors.ustc.edu.cn/simple/](https://pypi.mirrors.ustc.edu.cn/simple/)

#### 临时修改：

可以参考[清华大学镜像](https://mirrors.tuna.tsinghua.edu.cn/help/pypi/)或[阿里云镜像](https://blog.csdn.net/dulingwen/article/details/105865057?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~all~first_rank_v2~rank_v28-1-105865057.nonecase&utm_term=config%20pip%E9%85%8D%E7%BD%AE%E6%BA%90global&spm=1000.2123.3001.4430)配置。当然用下面的方式简单粗暴

可以在使用pip的时候在后面加上-i参数，指定pip源。

> pip install scrapy -i https://pypi.tuna.tsinghua.edu.cn/simple

#### 永久修改：

> pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple

### 3.使用pip安装几个写代码需要的包

这一步并不是必须的。但建议安装。**[flake8和yapf](https://www.baidu.com/link?url=A4QhpdeHsai8WgT40kuoRGDfrU__tAYO_JApw8bcWfAGkIdrcOVixeqJs02aLUbuEO33sfC3s41vivdBXnCXkq&wd=&eqid=88da30a20015e573000000065f9f5835)，有助于你代码整洁规范。**

### 4.配置王牌工具Jupyter Notebook

说她是王牌，[因为太好用了](https://sspai.com/post/56991)。她给的感觉就像R语言里的Rmarkdown。在里面可以任意书写代码块，实时输出各种图片和结果。

新版VS Code已经原生支持她了 [Jupyter](https://www.cnblogs.com/dogecheng/p/11904286.html)。Ctrl+Shift+P输入 Create Jupyter，然后创建即可。当然如果你还没有安装，系统会自动提示安装。安装完成后，就可以享用了。当然，你也可以先通过pip安装好Jupyter

![image](https://upload-images.jianshu.io/upload_images/943143-8fef2896231fac27.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```#%%```是Jupyter的预定义符号, 写上它就可以开始在py文件里愉快地写代码了! 在py文件里写了*#%%*这个之后就多了一个 Run cell在代码上面, 点击就可以跑出结果了。为了导出结果，我们还需要安装一个包 *nbconvert*。请在命令行输入

> pip install nbconvert

好了我们的配置基本完成了，那么大家可以试试运行一下以下的示例代码了。当然是同时用Jupyter Notebook输出4个代码块。然后导出为html


#### 输出Hello World
```python
 msg = "Hello World"
 print(msg)
```
#### 用matplotlib包搞个sin函数
```python
# sin 函数(这个需要用pip安装matplotlib包)
import matplotlib.pyplot as plt
import matplotlib as mpl
import numpy as np

x = np.linspace(0, 20, 100)
plt.plot(x, np.sin(x))
plt.show() 
```
#### Python 之禅
``` python
import this
```

#### 我们在之前做的那个“逢7过”
``` python
i = 0
while i <= 99:
  i += 1
  if i % 7 == 0 or i % 10 == 7 or i//10 == 7:
    continue
  else:
    print(i)
```
