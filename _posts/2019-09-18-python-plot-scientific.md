---
layout: post
title: python plot 科学计数法
categories: python
description: some word here
keywords: python, plot, scientific
---

```python
from matplotlib import ticker
from matplotlib.ticker import ScalarFormatter

formatter=ticker.ScalarFormatter(useMathText=True)

formatter.set_scientific(True)

formatter.set_powerlimits((-3,0))

ax2.yaxis.set_major_formatter(formatter)　　　
```
