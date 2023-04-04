

## 相关工具版本

1. node: 12.14.0
2. npm: 6.4.1
3. MongoDB: 5.0.3

## 功能
- [x] 登陆注册
- [x] 单聊
- [x] 群聊
- [x] 历史消息
- [x] ~~图片发送~~
- [x] 表情发送
- [x] 白板协作
- [x] 音视频聊天
- [x] 消息已读提醒
- [x] 好友分组
- [x] 好友备注
- [x] 好友上线提醒
- [x] 在线用户头像高亮
- [x] 添加好友
- [x] 添加群聊
- [x] 朋友圈功能
- [x] 发表朋友圈
- [x] 好友朋友圈
- [x] 朋友圈动态点赞
- [x] 朋友圈动态评论
- [x] 朋友圈动态回复评论
- [x] 日程设置

## 启动项目

### 1、克隆项目

```bash
git clone git@github.com:kaisersamamoon/boke.git
```

或者下载压缩包解压也可以。

### 2、启动MongoDB数据库

```bash
mongo
```

### 3、启动服务器

```bash
cd chatServer
npm install
# 初始化数据库，初始化成功后可以看到自动创建了chat数据库
node init.js
node app.js
```

### 4、启动客户端
```bash
cd chatClient
npm install
npm run dev
```

启动成功后访问[127.0.0.1:8080](127.0.0.1:8080)即可访问。

### 5、启动管理员端（3000端口）
```bash
cd chatAdmin
npm install
npm start
```

启动成功后访问[127.0.0.1:3000](127.0.0.1:3000)即可访问。

### 6、Q&A

按照上述步骤启动一般是不会出问题，有问题请首先排查是否**执行顺序**不一致，以及数据库是否启动。


## 项目截图

### PC端

#### 1、主页
![主页](./document/screenshots/p-home.png)

#### 2、聊天
![聊天](./document/screenshots/p-chat1.png)
![已读设置](./document/screenshots/p-chat2.png)
![通知](./document/screenshots/p-notify.png)

#### 3、朋友圈
![朋友圈](./document/screenshots/p-pyq1.png)
![朋友圈评论](./document/screenshots/p-pyq2.png)

#### 4、主题设置
![主题](./document/screenshots/p-theme.png)

#### 5、日程
![日程](./document/screenshots/p-schedule1.png)
![新建日程](./document/screenshots/p-schedule2.png)

#### 6、个人中心
![设置](./document/screenshots/p-personcenter.png)

### 移动端

#### 1、登录
![移动端](./document/screenshots/m-login.png)

#### 2、聊天列表
![移动端](./document/screenshots/m-aside.png)
![移动端](./document/screenshots/m-conversationlist.png)

#### 3、聊天界面
![移动端](./document/screenshots/m-chat.png)

#### 4、图片预览
![移动端](./document/screenshots/m-picpreview.png)

#### 5、换肤
![移动端](./document/screenshots/m-theme.png)

#### 6、朋友圈
![移动端](./document/screenshots/m-pyq.png)

## 系统功能图

### 普通用户
![普通用户功能设计0404](./document/普通用户功能设计0404.png)

### 管理员
![普通用户功能设计0404](./document/系统管理员功能设计0404.png)

## 技术路线

> 本系统分为`Client`，`Server`，`Admin`三个端：其中`Client`为客户端，`Server`为服务器端，`Admin`为管理员端。使用前后端分离的开发模式

- 客户端使用`Vue`、`VueX`、`Vue-Router`；
- 管理员端使用`React`、`antd`；
- 后端使用的是`node.js`；
- 数据库使用的是`MongoDB`；
- 在实现聊天的全双工数据通信使用的是`WebSocket`、`socket.io`。

## 项目打包

1. 客户端的代码打包后资源默认放在`chatServer`文件夹的`public`目录下；
2. 管理员端在`chatAdmin`的`build`目录下，需要自己自己手动将整个build目录复制到`chatServer`文件夹的`public`目录下，然后修改`build`目录文件的`index.html`中引入资源路径前都加上`/build`。

