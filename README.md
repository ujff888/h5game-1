# h5game
io类型h5游戏，客户端使用ts版cocos creator。服务器使用golang actor分布式框架,可伸缩部署。
[demo试玩地址](http://magicsea.top:8081/web-mobile/)

## 客户端依赖
- cocos creator 1.8

## 服务器源码依赖
```
go get github.com/AsynkronIT/protoactor-go  
go get github.com/gorilla/websocket
go get github.com/go-redis/redis
go get github.com/magicsea/ganet
```
==另外依赖protobuf,需要科学上网下载,没条件的下载我网盘里的[ google库](http://pan.baidu.com/s/1qYjUHJY)==

## 服务器运行 
- 安装数据库redis
- 编译go install Server
- 配置server/bin/config.json是数据库地址、服务器集群的配置地址
```
"redis":{
		"addr":"127.0.0.1:6379",//redis地址
		"password":"1111",//redis密码,未设密码可不填
		"poolsize":10,
		"dbs":[0,1,2,3,4]
	},

"proto":"json",//消息参数协议打包方式,支持protobuf,json
```

- 启动
```
- windows 执行 StartSingleServer.bat(单进程方式) 或者 StartMultiServer.bat(多进程方式)
- linux 执行./run.sh start
```
## TODO:
- [x] 登录、聊天、个人信息修改、基本战斗
- [x] behavoior接入
- [x] tcp,websocket协议兼容。pb,json可选。
- [ ] 移动降低发包，客户端平滑

## QQ群：285728047
