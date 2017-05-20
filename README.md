扫码登录(golang websocket)
========================

第一次写golang程序，用来学习的。 模拟PC浏览器二维码扫描登录的过程，手机APP端用 微信 模拟，简单起见，APP端只要发送token给服务端就算登录，服务端主动提示登录成功信息。

依赖包
* golang 1.5 version
* golang.org/x/net/websocket
* github.com/skip2/go-qrcode

clone项目到本地，安装依赖，然后 `go run qrlogin.go`。需要修改服务器的ip地址，局域网地址或者公网地址IP地址都行，手机能访问到就行。

### 流程

例如我这里手机和电脑均在局域网，PC的IP地址为 `192.168.110.141`

1. PC 浏览器访问 `http://192.168.110.141:7777/` 显示二维码，长连接建立
2. 手机微信 扫描二维码，跳转到某一个带有token的url（通常手机端会拿到token，带着用户信息和token给服务端验证)
3. 服务端验证token，通知PC端登录成功


