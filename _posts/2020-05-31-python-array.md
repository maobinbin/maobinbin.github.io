---
layout: post
title: python array基本操作
categories: python
description: python基本程序语言
keywords: mac
---



```python
data=np.r_[data,data_add]
```
稀疏矩阵初始化以及对角化
```python
# initial the matrix to sparse coo form
H_coo = sparse.coo_matrix((data,(row,col)),shape=(Lx*Ly,Lx*Ly))
# change the sparse matrix to csr form
H_csr=H_coo.tocsr()
#print (cc.toarray())
from scipy.sparse.linalg import eigsh
eig_H,vec_H=eigsh(H_csr, k=Lx*Ly-2, which='LM', v0=None, maxiter=None, tol=0)

H_dense=H_csr.todense()
#print (cc.todense())
[eig_H_den,vec_H_den]=np.linalg.eigh(H_dense)
```


