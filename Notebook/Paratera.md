# Paratera 并行

Operating System: CentOS Linux 7 (Core)

Paratera use [[Slurm]] to schedule and manage jobs.

`$` 表示后面命令在终端运行

## 编译 Einstein Toolkit

- module load 依赖包
	```bash
	$ source /public1/soft/modules/module.sh
	$ source /public1/home/sc31924/.bashrc
	```
- 编译
	```
	$ cd ~/Cactus
	$ make <name>-config options=/public1/home/sc31924/generic.cfg THORNLIST=/public1/home/sc31924/einsteintoolkit.th CC=gcc FC=gfortran CXX=g++
	$ make <name>
	```

注：添加新的 Thorn 需将源代码上传至 `~/Cactus/arrangements` 相应位置并修改 `einsteintoolkit.th` 文件。

### Environment Modules

The Environment Modules package is a tool that simplify shell initialization and lets users easily modify their environment.

```shell
$ module list             # List all the currently loaded modules.
$ module avail            # List the available modules.
$ module load <modules>   # Load the named module.
$ module unload <modules> # Unload the named module.
$ module show <modules>   # Show details about the module.
```

## 运行 Einstein Toolkit
 
- 查看队列
```bash
$ sinfo   #idle 是空闲节点，alloc 是已被占用节点，comp 是正在释放资源的节点 v3_64，v3_128这两个分别是64G内存，128G内存 Big_jog是大作业队列，有10个节点以上的作业建议提交到这个队列
```
- `~/Desktop/Cactus` 脚本中 `<参数>` 根据需求修改
```bash
#!/bin/bash
#SBATCH -N <节点数>
#SBATCH -n <核数>
#SBATCH -c <线程>
#SBATCH -p <队列 v3_64>
#SBATCH --time=<时间 0-01:00:00>
#SBATCH --output=/public1/home/sc31924/Desktop/output/slurm-%j.out
#SBATCH --error=/public1/home/sc31924/Desktop/output/slurm-%j.err

export OMP_NUM_THREADS=$SLURM_CPUS_PER_TASK
export CACTUS_NUM_THREADS=$SLURM_CPUS_PER_TASK
export CACTUS_NUM_PROCS=${SLURM_NPROCS}
export CACTUS_STARTTIME=$(date +%s)

exe=$1
par_filename=$2
name=${par_filename%.*}

source /public1/soft/modules/module.sh
source /public1/home/sc31924/.bashrc

echo "Starting:"
set -e

dir="/public1/home/sc31924/Desktop/CactusPar"

cd /public1/home/sc31924/simulations
srun -N <节点数> -n <核数> -c <线程> /public1/home/sc31924/Cactus/exe/cactus_${exe} -L 3 $dir"/"$par_filename

echo "Done."
```
- 提交任务
```bash
$ cd ~/Desktop
$ ls CactusPar/
$ sbatch cactus.sh <exe> <XXX.par> # <exe>为编译好的名字，如zou。注意参数文件名，确保不覆盖原有文件夹！
```
- 查看作业状态 
```bash
$ squeue   # R表示正常运行，PD表示在排队
```
- Cancel a job
```bash
scancel <JOBID>
```
- Monitoring your jobs 
```bash
$ ssh <NODE>   # 登陆到计算节点
$ top          # 查看CPU使用率
$ exit         # 返回到登陆节点
```

```bash
if [ -d /public1/home/sc31924/simulations/${name} ]; then
    rm -rf /public1/home/sc31924/simulations/${name}
fi
```