## Paratera

Paratera use [[Slurm]] to schedule and manage jobs.

## papp_cloud

- Download
	```bash
	$ wget https://www.paratera.com/archive/static/media/uploads/softwares/ParaAPP/papp_cloud -3.1.7.zip
	```
- Install
	```bash
	$ unzip papp_cloud-3.1.7.zip
	$ cd papp_cloud-3.1.7
	$ ./install.sh install
	```
- Login accounts
	```bash
	$ papp_cloud login -u user@paratera.com -p
	$ papp_cloud accounts
	```
- Login
	```bash
	$ papp_cloud ssh <paratera@gz>
	```
- Mount
	```bash
	$ papp_cloud sshfs <paratera@gz>:<folder> <folder>
	```

## Environment Modules

The Environment Modules package is a tool that simplify shell initialization and lets users easily modify their environment.

```bash
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

## python

### 使用 Conda

- load 必要模块
```bash
source /public1/soft/modules/module.sh
module load anaconda/python3.6.5-tensorflow1.8.0-thc
source activate nlp
```
- 联网
```bash
export http_proxy=http://172.16.3.223:8888
export https_proxy=http://172.16.3.223:8888
```


## Debug

- locale
```bash
export LC_ALL="en_US.UTF-8"
export LC_CTYPE="en_US.UTF-8"
```

```bash
export LC_ALL=C
```

- libfabric.so.1
```bash
source <mpi/bin>/mpivars.sh
```

- `-lz`
```bash
module avail zlib
```
