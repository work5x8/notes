```shell
# 这个命令用来开启Go模块支持
go env -w GO111MODULE=on
# 代理
go env -w GOPROXY=https://goproxy.cn,direct
# 私有
go env -w GOPRIVATE='git.xxx.com'

```
