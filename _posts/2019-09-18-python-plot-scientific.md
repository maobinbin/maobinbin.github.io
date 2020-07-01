---
layout: post
title: python plot 科学计数法
categories: python
description: some word here
keywords: python, plot, scientific
---

1.

```python
from matplotlib import ticker
from matplotlib.ticker import ScalarFormatter
formatter=ticker.ScalarFormatter(useMathText=True)
formatter.set_scientific(True)
formatter.set_powerlimits((-3,0))
ax2.yaxis.set_major_formatter(formatter)　　　
```

2.
```python
ax = plt.gca()  # 获取当前图像的坐标轴信息
ax.xaxis.get_major_formatter().set_powerlimits((0,1)) # 将坐标轴的base number设置为一位。
ax.yaxis.get_major_formatter().set_powerlimits((0,1))
```

3. log
```python
ax.set_yscale('log')
```
