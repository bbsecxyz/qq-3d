# qqgroup-visualization




## *目前项目连接的是我个人的数据库，可直接npm run start运行，如果我的数据库失效，请下载数据库备份文件自己配置数据库*

## 1.配置数据库（需要300GB以上磁盘剩余空间）
+ 下载并安装SqlServer2008R2，配置好用户名以及登录密码，如果远程连接数据库的话，需配置数据库允许远程登录（SqlServer数据库配置请自行搜索教程）
内网10.6.65.1 社工库 QQ 下载
+ 解压下载的压缩包，得到数据库备份文件，恢复数据库备份文件到SqlServer（SqlServer恢复数据库恢复操作请自行搜索教程）

## 2.搭建服务端（需要支持Nodejs的操作系统，CPU1核以上剩余内存1GB以上）
+ 下载安装[Node.js](https://nodejs.org/en/)环境
+ npm全局安装webpack和webpack-dev-server
``` bash
# 全局安装webpack
npm install webpack -g

# 全局安装webpack-dev-server
npm install webpack-dev-server -g
```
## 3.配置数据库连接
+ 进入项目目录下
+ 打开db.json文件
+ 修改其中的数据库连接信息为自己的数据库连接信息（默认的数据库连接信息是我本人的服务器上的数据库，不保证可用）
+ db.json例子
``` json
{
    "server": "服务器地址",
    "database": "数据库名称",
    "user": "请输入用户名",
    "password": "请输入数据库用户密码"
}
```

## 4.运行
+ 进入项目目录下
``` bash
# 安装依赖
npm install

# 运行系统
npm run start
```

## 操作系统要求
+ 因为使用的数据库是SqlServer数据库，所以推荐使用Windows操作系统
+ 当然服务端使用的是Node，如果你连接到的是远程的SqlServer数据库的话，是可以使用任何支持Node的系统的

## 数据库说明
+ 数据库请使用SqlServer2008R2或更新版本的SqlServer
+ 数据库说明
    + 索引说明
        + 我没有修改数据，只是在QQ号字段以及群号字段上加了索引用来优化查询速度
    + 存储过程说明
        + queryByGroupNum 传入群号查询关联的力导向图数据
        + queryByQQNum 传入QQ号查询关联的力导向图数据
        + queryByQQNumExt 传入QQ号进行二层关联查询，得出力导向图数据
        + queryTableByGroupNum 传入群号查询群成员信息表
        + queryTableByQQNum 传入QQ号查询QQ加群信息表
        
