# go的安装和环境配置

## 下载和配置环境变量

去官网下载，将安装目录下的bin目录添加环境变量，需要新建个变量GOROOT,值为go的安装路径，也就是bin目录的父目录，还需要在path里新加一个go的bin的路径,windows不赘述

linux需要在~/.bashrc文件末尾加上

```shell
export GOROOT=/usr/local/go
export PATH=$PATH:$GOROOT/bin
```

之后执行`source ~/.bashrc`使得配置生效。新开一个终端，在终端键入`go version`，输出`go version go1.20.4 linux/amd64`表示go的环境变量配置完成

## go mod 和 proxy配置

go 的高版本采用go mod作为包管理工具，所以我们不必像低版本一样配置gopath，只能在gopath目录下写代码，所以我们这里需要配置下go mod

在终端键入 `go env`会看到结果中`GO111MODULE=""`这个就是go mod的开关，我们需要键入`go env -w GO111MODULE=on`  ,再次输入`go env`，就能看到`GO111MODULE="on"`表示go mod已经开启

`go env`环境变量中有个变量`GOPROXY`允许对下载源进行控制，设置了这个变量，就会开启Go模块代理，可以提高下载依赖的稳定性和速度

`go env -w GOPROXY=https://goproxy.cn,direct`再次输出`go env`就可以看到代理设置成功



## vscode go开发环境配置

下载vscode ，安装go扩展（第一个 star最多的），

如果觉得编译运行麻烦，可以安装个code runnner

