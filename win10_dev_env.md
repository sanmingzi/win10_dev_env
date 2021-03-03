# 开发环境配置: Win10 + WSL2 + Ubuntu-18.04 + Docker

## WSL2

- 开启虚拟化
- 升级系统
- 升级内核

## Ubuntu-18.04

- 安装 Ubuntu-18.04
- [设置apt源](https://www.cnblogs.com/dream4567/p/9690850.html)

## Docker

[使用国内源为Ubuntu18.04安装Docker](https://www.jianshu.com/p/9b1dd79b5708?tdsourcetag=s_pcqq_aiomsg)

```
sudo service docker start
docker info
docker run hello-world
docker image ls
docker container ls
```

## 文件共享

默认情况下，在 WSL2 的 /mnt 目录下可以找到对应的 Win10 的文件。但是，如果我们直接将 /mnt 下面的文件 mount 到 docker 中会有一些问题：

1. 速度很慢
2. 文件无法热加载

最好的做法是将文件直接放到 WSL2 中去。我是这样做的：

```
cp -r /mnt/e/workspace /
sudo chown -R username:groupname /workspace
```

将工作目录直接转移到根目录下，然后改变文件权限。
