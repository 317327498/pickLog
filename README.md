# pickLog
## 自动从公司服务器集群下载指定应用日志
公司有个应用部署平台，重启测试环境需要在应用部署平台重启，然后拿到IP去数据库找到IP对应的服务器账号密码，然后登陆服务器查看对应日志。
公司有上百个服务器集群。每次这样重复操作很烦。然后就做了个小工具，编译成exe文件，一键运行。

安装四个依赖包

	1. 安装 ssh包
      1) 新建 $GOPATH/src/golang.org/x
      2) git clone https://github.com/golang/crypto.git
  	2. 安装 sftp 包
      1) go get https://github.com/pkg/sftp
  	3. 按任意键退出
      1) go get https://github.com/nsf/termbox-go
  	4. go-mysql包
      1) go get github.com/go-sql-driver/mysql

实现思路：
1. 模拟登陆部署平台
2. 拿到应用对应的ip去数据库查账户密码
3. 拿到服务器信息ssh登陆并下载指定文件
