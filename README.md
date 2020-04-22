# golang定制版本，适合流量录制回放

修改golang源码，Hook相关调用，并对外暴露接口，如：OnAccept、OnConnect、OnRead、OnWrite等等。

所有的源码修改都通过了golang官方的测试，详见1.3源码安装分支。「 测试方法：cd src && ./all.bash 」

目前支持的版本如下，不定期会同步官方最新release版本。

* go1.10【基于官方go1.10.8 源码修改】
* go1.11【基于官方go1.11.13源码修改】
* go1.12【基于官方go1.12.17源码修改】
* go1.13【基于官方go1.13.9 源码修改】
* go1.14【基于官方go1.14.1 源码修改】

> 流量录制和回放，参考：[https://github.com/didi/sharingan](https://github.com/didi/sharingan)

## 一、安装方法

### 1.1、脚本安装【推荐】

* 默认安装目录：/tmp/recorder-${GO-VERSION}，如：/tmp/recorder-go1.10。
* 包含远程版本对比、本地自动升级等等，目前只支持linux和mac下面的64位系统。
* /tmp是临时目录，如有需要可以cp到有权限的目录方便长期使用。
* github国内下载不稳定，经常出现超时，可以试试访问google的方法。

``` bash
## go1.10版本安装
curl https://raw.githubusercontent.com/didi/sharingan-go/recorder/install/go1.10 | sh
export GOROOT=/tmp/recorder-go1.10
export PATH=$GOROOT/bin:$PATH

## go1.11版本安装
curl https://raw.githubusercontent.com/didi/sharingan-go/recorder/install/go1.11 | sh
export GOROOT=/tmp/recorder-go1.11
export PATH=$GOROOT/bin:$PATH

## go1.12版本安装
curl https://raw.githubusercontent.com/didi/sharingan-go/recorder/install/go1.12 | sh
export GOROOT=/tmp/recorder-go1.12
export PATH=$GOROOT/bin:$PATH

## go1.13版本安装
curl https://raw.githubusercontent.com/didi/sharingan-go/recorder/install/go1.13 | sh
export GOROOT=/tmp/recorder-go1.13
export PATH=$GOROOT/bin:$PATH

## go1.14版本安装
curl https://raw.githubusercontent.com/didi/sharingan-go/recorder/install/go1.14 | sh
export GOROOT=/tmp/recorder-go1.14
export PATH=$GOROOT/bin:$PATH
```

### 1.2、二进制安装

支持的二进制安装包如下：

* [go1.10.darwin-amd64.tar.gz](https://github.com/didi/sharingan-go/releases/download/go1.10.recorder/go1.10.darwin-amd64.tar.gz)
* [go1.10.linux-amd64.tar.gz](https://github.com/didi/sharingan-go/releases/download/go1.10.recorder/go1.10.linux-amd64.tar.gz)
* [go1.11.darwin-amd64.tar.gz](https://github.com/didi/sharingan-go/releases/download/go1.11.recorder/go1.11.darwin-amd64.tar.gz)
* [go1.11.linux-amd64.tar.gz](https://github.com/didi/sharingan-go/releases/download/go1.11.recorder/go1.11.linux-amd64.tar.gz)
* [go1.12.darwin-amd64.tar.gz](https://github.com/didi/sharingan-go/releases/download/go1.12.recorder/go1.12.darwin-amd64.tar.gz)
* [go1.12.linux-amd64.tar.gz](https://github.com/didi/sharingan-go/releases/download/go1.12.recorder/go1.12.linux-amd64.tar.gz)
* [go1.13.darwin-amd64.tar.gz](https://github.com/didi/sharingan-go/releases/download/go1.13.recorder/go1.13.darwin-amd64.tar.gz)
* [go1.13.linux-amd64.tar.gz](https://github.com/didi/sharingan-go/releases/download/go1.13.recorder/go1.13.linux-amd64.tar.gz)
* [go1.14.darwin-amd64.tar.gz](https://github.com/didi/sharingan-go/releases/download/go1.14.recorder/go1.14.darwin-amd64.tar.gz)
* [go1.14.linux-amd64.tar.gz](https://github.com/didi/sharingan-go/releases/download/go1.14.recorder/go1.14.linux-amd64.tar.gz)

### 1.3、源码安装

如果以上安装方法不支持您的系统，可以考虑使用源码安装，支持的源码git分支如下：

* [recorder-branch.go1.10](https://github.com/didi/sharingan-go/tree/recorder-branch.go1.10) 【对应官方release-branch.go1.10】
* [recorder-branch.go1.11](https://github.com/didi/sharingan-go/tree/recorder-branch.go1.11) 【对应官方release-branch.go1.11】
* [recorder-branch.go1.12](https://github.com/didi/sharingan-go/tree/recorder-branch.go1.12) 【对应官方release-branch.go1.12】
* [recorder-branch.go1.13](https://github.com/didi/sharingan-go/tree/recorder-branch.go1.13) 【对应官方release-branch.go1.13】
* [recorder-branch.go1.14](https://github.com/didi/sharingan-go/tree/recorder-branch.go1.14) 【对应官方release-branch.go1.14】

> 源码安装参考：[https://golang.org/doc/install/source](https://golang.org/doc/install/source)

## 常见问题

* 1、Failed to connect to raw.githubusercontent.com port 443: Connection refused

A：github国内下载不稳定，经常出现超时，可以试试访问google的方法，或者参考搞一个内网gitlab版本。
