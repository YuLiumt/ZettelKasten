## Linux

## Terminal

So, basically, a shell is a program that receives commands from the user and gives it to the OS to process, and it shows the output.

## Commands

### find
Locate files within a given directory
```bash
find . -name "*.c"
```

### which

### whereis

### top

For Memory usage, the number you are interested in is RES

### scp

```bash
scp -r -l 8192 yuliu@172.22.127.9:/home4/yuliu/ /Users/liuyu/
```

### rsync

```bash
rsync -avu --progress --delete --exclude=\".*\" --exclude=\"__pycache__\" yuliu@172.22.127.9:/home4/yuliu/Desktop/Pylib/CactusTool/CactusTool /Users/liuyu/Desktop/CactusTool/
```