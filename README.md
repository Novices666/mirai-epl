# mirai-epl
基于mirai-api-http的易语言QQ机器人框架，开发ing...

A Epl‘s QQ robot framework based on Mirai API HTTP, developing...

***
## 更多信息
[mirai](https://github.com/mamoe/mirai)：一个在全平台下运行，提供 QQ Android 协议支持的高效率机器人库

[mirai console loader](https://github.com/iTXTech/mirai-console-loader)：模块化、轻量级且支持完全自定义的 mirai 加载器

[mirai-api-http](https://github.com/project-mirai/mirai-api-http)：提供HTTP API供所有语言使用mirai

***
## 介绍
  本项目基于`mirai-api-http`的`websocket server` 接口实现易语言对`mirai`的调用
## 环境配置

### 安装`mirai console loader`

  #### 一键安装(推荐)

[iTXTech MCL Installer](https://github.com/iTXTech/mcl-installer) 能在所有操作系统上一键安装 `iTXTech MCL`
  #### 手动安装

请参考 [手动安装MCL](https://github.com/iTXTech/mirai-console-loader#%E6%89%8B%E5%8A%A8%E5%AE%89%E8%A3%85)
### 安装`mirai-api-http`

请参考 [安装mirai-api-http](https://github.com/project-mirai/mirai-api-http#%E5%AE%89%E8%A3%85mirai-api-http)
  请安装最新版，本项目会随`mirai-api-http`的更新而更新
### 配置`mirai-api-http`

  1.编辑`config/net.mamoe.mirai-api-http/setting.yml`配置文件 (没有则自行创建)
  2.启动MCL `./mcl`
#### setting.yml模板

```yaml
cors: 
  - '*'

adapters:
 - ws

## authKey会自动生成
authKey: xxxxxxx
## verifyKey 请自行设置，用于后续的连接操作，也可直接删除本属性，mirai-api-http会自主生成，若删除请在mcl启动时记录verifyKey
verifyKey: xxxxxxxx
cacheSize: 4096
enableWebsocket: false
report: 
  enable: false
  groupMessage: 
    report: true
  friendMessage: 
    report: true
  tempMessage: 
    report: true
  eventMessage: 
    report: true
  destinations: []
  extraHeaders: {}

heartbeat: 
  enable: false
  delay: 1000
  period: 15000
  destinations: []
  extraBody: {}

  extraHeaders: {}
adapterSettings:
  ws:
    host: localhost
    port: 8080
    reservedSyncId: -1
```
### 在MCL中登陆bot

## 开始开发
（1）将本项目拉取(下载)到本地
（2）在ws_连接中填写ip地址，端口号，verifyKey及MCL中登陆的bot的QQ
（3）开始开发，您可以参考本项目中的写法
***
## 实现功能
- [x] 接收各类消息
  - [x] 好友消息
  - [x] 群消息
  - [x] 群临时消息
  - [x] 陌生人消息
  - [x] 其他客户端消息
  - [x] 同步消息
- [X] 获取插件信息（获取插件版本号和当前登陆的QQ）
  - [x] 获取插件版本号
  - [x] 获取当前所有登陆账号
- [X] 缓存操作
  - [x] 通过messageId获取消息
- [X] 获取账号信息（获取好友列表，群列表，群成员列表，Bot资料，好友资料，群成员资料，QQ用户资料）
  - [x] 获取好友列表
  - [x] 获取群列表
  - [x] 获取群成员列表
  - [x] 获取Bot资料
  - [x] 获取好友资料
  - [x] 获取群成员资料
  - [x] 获取QQ用户资料
- [ ] 消息发送与撤回
  - [ ] 发送好友消息
  - [ ] 发送群消息
  - [ ] 发送临时会话消息
  - [ ] 发送戳一戳消息
  - [ ] 撤回消息
  - [ ] 获取漫游消息

<details>
<summary>消息类型</summary>

  - 引用回复
  - @
  - @全体成员
  - QQ表情
  - 文字
  - 图片
  - 闪照
  - 语音
  - Xml
  - Json
  - App
  - 戳一戳
  - 骰子
  - 商城表情
  - 音乐分享
  - 转发消息
  - 文件
  - MiraiCode
</details>

- [ ] 文件操作
  - [ ] 查看文件列表
  - [ ] 获取文件信息
  - [ ] 创建文件夹
  - [ ] 删除文件
  - [ ] 移动文件
  - [ ] 重命名文件
- [ ] 账号管理
  - [ ] 删除好友
- [ ] 群管理
  - [ ] 禁言群成员
  - [ ] 解除群成员禁言
  - [ ] 移除群成员
  - [ ] 退出群聊
  - [ ] 全体禁言
  - [ ] 解除全体禁言
  - [ ] 设置群精华消息
  - [ ] 获取群设置
  - [ ] 修改群设置
  - [ ] 获取群员设置
  - [ ] 修改群员设置
  - [ ] 修改群员管理员
- [ ] 群公告
  - [ ] 获取群公告
  - [ ] 发布群公告
  - [ ] 删除群公告
- [ ] 事件处理
  - [ ] 添加好友申请
  - [ ] 用户入群申请
  - [ ] Bot被邀请入群申请
