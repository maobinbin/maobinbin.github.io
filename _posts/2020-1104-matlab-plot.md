---
layout: post
title: matlab命令行画图
categories: matlab,linux
description: matlab命令行画图,不显示figure界面
keywords: matlab
---

画图
```matlab
hf1=figure('visible','off');
set(0,'CurrentFigure',hf1);
scatter(myDr,d,3,"filled");
ylabel("Inverse Participation Ratio (log plot)");
xlabel("E");
saveas(gcf,'x.pdf')
save("myDr.dat",'myDr','-ascii');
```

后台任务提交
```shell
matlab  -nodesktop -nosplash < diagnalize_H_nxyz.m 1>running.log 2>running.err &
```
