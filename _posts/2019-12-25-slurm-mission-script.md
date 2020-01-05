---
layout: post
title: SLURM系统批量提交任务脚本
categories: [linux,slurm]
description: 批量提交任务脚本
keywords: slurm, sbatch, script
---

```shell
cat > ${TASK} << EOF
#!/bin/bash

#SBATCH --nodes=1
#SBATCH --cpus-per-task=4
#SBATCH --time=200:00:00
#SBATCH --mem-per-cpu=8gb
#SBATCH --job-name=task
#SBATCH --output=result.out
./main  > output
EOF

sbatch ${TASK}
```
