---
layout: post
title: mathematica plot
categories: mathematica
description: mathematica 画图设置相关
keywords: mathematica, plot
---

字母上添加tilde
ctr+&

**Plot**
```mathematica
Subscript[J, 0] = 0.9
Export["/home/maobinbin/nutstore/quantum optics/SPT_A2/fig_gc.pdf", 
 Plot[{Sqrt[1 - Sqrt[J^2]] /. J -> Subscript[J, 0], 
   Sqrt[(1 + \[Delta]^2 + Sqrt[
     4 \[Delta]^2 + 
      J^2 *(-1 + \[Delta]^2)^2])/(-1 + \[Delta]^2)^2] /. 
    J -> Subscript[J, 0], 
   Sqrt[(1 + \[Delta]^2 - Sqrt[
     4 \[Delta]^2 + 
      J^2 *(-1 + \[Delta]^2)^2])/(-1 + \[Delta]^2)^2] /. 
    J -> Subscript[J, 0]}, {\[Delta], 0, 1}, PlotRange -> {0, 4}, 
  Frame -> True, PlotStyle -> {Red, Blue, Green}, 
  PlotLegends -> {Style[
     "\!\(\*SubscriptBox[OverscriptBox[\(g\), \(~\)], \(0\)]\)", 
     Black, 18], 
    Style["\!\(\*SubscriptBox[OverscriptBox[\(g\), \(~\)], \(+\)]\)", 
     Black, 18], 
    Style["\!\(\*SubscriptBox[OverscriptBox[\(g\), \(~\)], \(-\)]\)", 
     Black, 18]}, FrameLabel -> {Style[\[Delta], Large], Style[
\!\(\*OverscriptBox[\(g\), \(~\)]\), Large]}, 
  FrameTicksStyle -> Directive[Black, 20], LabelStyle -> "All"]]
  
```
