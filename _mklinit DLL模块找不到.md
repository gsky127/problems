# 关于在PyCharm中import numpy 出现from . import _mklinit ImportError: DLL load failed: 找不到指定模块
关于在PyCharm中import numpy 出现from . import _mklinit ImportError: DLL load failed: 找不到指定模块
最近因为一些原因安装了Anaconda3并且重新配置Python环境，但是遇到了一些麻烦的事情。

首先就是在Anaconda已经装好numpy和mkl的情况下，在PyCharm中import numpy，会提示

from . import _mklinit  ImportError: DLL load failed: 找不到指定模块

但是在Jupiter和Spider里面都能正确import numpy，不会出现这个问题。

在网上找了很多解决方法（多数是说python版本和numpy版本不匹配等问题导致，需要重新安装），但都尝试无果。最后终于在https://www.jianshu.com/p/2418311bbad0这篇文章中找到了答案。

因为我以前是直接安装的python而没有用Anaconda的python，看到这篇文章才想起，在环境变量里面保留着原来的python路径，而没有添加Anaconda的路径，将如下的路径添加到PATH之后问题就解决了。
```
D:\software\anacoda\Scripts
D:\software\anacoda\
D:\software\anacoda\Library\bin
```
当然，我也看到有些文章（包括Anaconda安装时的提示）说不建议把Anaconda添加到环境变量，但是如果不添加到环境变量似乎就没办法解决PyCharm中无法import numpy这个问题，具体的原因我也不是很清楚，不知道有没有更好的办法，希望大家能够提出来，谢谢
