# Paratera 并行

## Linux

Operating System: CentOS Linux 7 (Core)

### 常用命令

```shell
which gcc
sbatch XXX.sh # 提交作业
sinfo # 查看队列 idle 是空闲节点，alloc 是已被占用节点，comp 是正在释放资源的节点 V3_64，V3_128这两个分别是64G内存，128G内存 Big_jog是大作业队列，有10个节点以上的作业建议提交到这个队列，
squeue # 查看作业状态 R表示正常运行，PD表示在排队
```

### SBATCH

```bash
#!/bin/bash
#SBATCH -p v3_64 # 队列
#SBATCH -N 1 # 节点数
#SBATCH -n 1 # 核数
#SBATCH -c  24
echo "Done!"
```

### Environment Modules

The Environment Modules package is a tool that simplify shell initialization and lets users easily modify their environment.

![image-20201207111415984](https://tva1.sinaimg.cn/large/0081Kckwgy1glf4dg2w2aj31ku09g0w7.jpg)

```sh
source /public1/soft/modules/module.sh
```

#### 常用命令

```shell
module list # List all the currently loaded modules.
module avail # List the available modules.
module load <modules> # Load the named module.
module unload <modules> # Unload the named module.
module show <modules> # Show details about the module.
```

## Einstein Toolkit

```shell
sbatch ./Cactus ET 1 XXX.par
```

### 编译

```
make ET-config options=/public1/home/sc31924/generic.cfg THORNLIST=/public1/home/sc31924/einsteintoolkit.th CC=gcc FC=gfortran CXX=g++
make ET
```

