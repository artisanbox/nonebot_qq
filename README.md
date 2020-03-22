# 定时任务—QQ机器人（Nonebot_QQ）

## 更新日志：
### 1.2.0 - 2020.3.21
- 优化：
    - 定时群消息与禁言功能（定时任务）
    - 时间输入逻辑
    - 人机交互逻辑
### 1.1.0 - 2020.3.20
- 新增：
    - 定时群禁言功能
    - @全体成员功能
- 优化：
    - 定时群消息功能
    - 人机交互逻辑
### 1.0.0 - 2020.3.19
- 新增：
    - 定时群消息功能

## 使用方法
- 回复机器人：'帮助' 即可获取帮助指令
- 配置机器人QQ号：config/py 中的QQ号修改为自己的即可
- 设置群号和个人QQ号：在 function/plugins 中的 report.py 中修改
- 注意：机器人QQ号与个人QQ号非同一QQ
- 具体问题参看下方

## 安装方法：
- https://nonebot.cqp.moe/guide/installation.html

## 配置环境：
- nonebot ```pip install nonebot```
- scheduler ```pip install "nonebot[scheduler]"```

## 安装配置:
安装完成后，再次配置CQHTTP插件，在CQHTTP插件的目录下在 config/ 下，打开名为 “user-id”.json 的文件（“user-id” 为你登录的 QQ 账号）
修改文件为如下配置项:
```
{
  "ws_reverse_api_url": "ws://127.0.0.1:8080/ws/api/",
  "ws_reverse_event_url": "ws://127.0.0.1:8080/ws/event/",
  "use_ws_reverse": true
}
```
配置好后重启插件，运行我写的Python文件（bot.py），若配置成功,控制台应该会输出以下内容:

```
[2019-10-01 15:55:21,745] 127.0.0.1:50971 GET /ws/api/ 1.1 101 - 1031
[2019-10-01 15:55:22,044] 127.0.0.1:50972 GET /ws/event/ 1.1 101 - 996
```

这表示 CQHTTP 插件已经成功地连接上了 NoneBot，与此同时，插件的日志文件中也会输出反向 WebSocket 连接成功的日志。

## 更新计划：
- 产品定位：
    -【核心】1.定时任务：
        -a.任务：群禁言，定时群消息，定时个人消息

### 1.2.2 - 2020.4.1前完成
- //新增数据初始化交互
- //优化数据存储结构
    - report.py => default.py 
        - '初始化' => 获取群号，机器人QQ号，控制QQ号
        - 数据存放 => data[group,Bot,self].txt: session.get() 获取 numbers 写入文件
        - 数据读取 => data[group,Bot,self].txt
	
### 1.2.3 - 2020.4.15前完成
- 定时多个群消息

### 1.2.4 - 2020.4.20前完成
- 定时多个个人消息

### 1.2.5 - 2020.5.1前完成
- 新增取消任务
- 查看当前未执行任务

### 1.3 - 2020.5.15前完成
- 优化Bug，增加代码的稳定性
