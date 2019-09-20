---
layout: post
title: python批量读写数据
categories: python
description: some word here
keywords: python, data
---
```python
file_name="data_c_fixed_T_L1_iter_%d_CDLiter_%d_chi_%d.txt" %(n_iter,n_CDL,D_CDL_cut)
np.savetxt(file_name,central_charge_all)

file_name="./iter_%02d_CDL_%02d_chi_%02d/data_c_fixed_T_L1_iter_%d_CDLiter_%d_chi_%d.txt" %(n_iter,n_CDL,D_CDL_cut,n_iter,n_CDL,D_CDL_cut)
central_charge_all=np.loadtxt(file_name)
```
