# docker_kong
docker 下 部署 webapi 网关：Kong

#### 数据映射
修改 docker-compose.yml 中的 volumes 项，将相关数据映射到本地主机

#### 验证
* 浏览器打开：http://127.0.0.1:8001/ ，如果现实的是json数据，表示可以kong正常启动
* 浏览器打开：http://127.0.0.1:8080/ ，现实界面如下
![Markdown](http://i4.bvimg.com/599630/be18bcb6291e1d7a.png)
表示可以用 kong-dashboad管理 kong
* 填写 Kong node URL 时注意，ip地址需要使用 非 `localhost` 和 `127.0.0.1` 的内容，需要使用以及获取的ip地址，获取方式是在cmd中执行`ipconfig`,比如我获取的ip地址如下
![Markdown](http://i4.bvimg.com/599630/d049e9b5f064b8a2.png)
看红色方框内ip地址，所以填写的kong node url 地址是：http://192.168.1.112:8001,然后执行save，显示如下界面
![Markdown](http://i4.bvimg.com/599630/011019614b25b08e.png)
表示kong安装以及kong-dashboad安装成功

#### 其他
关于 输入 kong node url 使用ip地址方式，待测试的一种方式是给每个容器一个ip地址，然后使用link让容器关联，通过配置容器内部ip地址，是否可行，有待测试

#### 扩展
kong 高可用
kong-database 高可用

#### 任务
[X] 编写docker-compose.yml
[ ] 使用容器内部ip地址
[ ] 高可用 
