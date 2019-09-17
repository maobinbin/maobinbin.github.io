---
layout: post
title: sparse matrix: scipy.sparse
categories: python
description: some word here
keywords: python, sparse matrix, scipy
---
from scipy import sparse
import scipy.sparse.linalg as sparse_la

# H_row, H_col, H_val are 1D arrays
H_matrix = sparse.coo_matrix((H_val,(H_row,H_col)),shape=(np.power(3,L),np.power(3,L)))

vals, vecs = sparse_la.eigsh(H_matrix,which='SR' , k=50)

H_matrix_dense=sparse.coo_matrix.todense(H_matrix,out=None)
