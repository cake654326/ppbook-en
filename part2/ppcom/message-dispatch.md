# PPCom Message Dispatch Policy

`Service Agent Administrator` can set `PPCom Message Dispatch Policy` in `PPConsole/Team Settings/Message Dispatch`. Dispatch Policy decides which service agents should be added to chat when `PPCom User` establishs chat with service agents.

--------

#### Target Service Agents

`Target Service Agents`: When `PPCom User` establishs chat with service agents, service agents who can be added to the chat is `Target Service Agents`.

当用户点击PPCom`聊天图标`或者`开始对话输入框`时，如果之前没有建立过对话，那么系统就会寻找能为他服务的`目标客服`，之后建立该用户和`目标客服`之间的对话。

系统寻找`目标客服`的结果和客服的状态息息相关，客服的状态有：
  
    > 离线：PC上登录的客服，一旦主动登出或者与服务器断开连接，即视为离线；移动设备上登录的客服，只有在主动登出后才视为离线。
    > 在线：客服在PC上登录，并保持和服务器的连接，视为在线；在移动设备上登录，即使断开和服务器连接，也视为在线，只有在主动退出登录后，才视为离线。
    > 忙碌：客服登录后，处于在线状态时，可以主动把自己的状态设为忙碌，系统不会给处于忙碌状态下的客服分配对话。
    > 空闲：客服登录后，处于在线状态时，可以主动把自己的状态设为空闲，当PPCom用户请求建立和客服对话时，处于空闲状态的客服有机会加入到对话中。
    
客服管理员设置的消息分发策略最终决定了哪些客服会成为`目标客服`。


#### 消息分发策略

**All**

ALL策略下，PPCom用户在和客服建立对话时，客服团队里所有的客服都是`目标客服`，系统总是会把客服团队里所有的客服加入到这个对话中。


**SMART**

SMART策略下，用户在和客服建立对话时，系统会寻找客服团队里在线且处于空闲状态的客服。如果找到符合条件的客服，则从中选取一个客服加入到这个对话中。否则就按ALL策略，把所有的客服都加入到这个对话中。


**GROUP**

GROUP策略下，用户有两种方式建立对话，第一种是通过点击PPCom`聊天图标`或者`开始对话输入框`建立对话（通用方法），第二种是通过点击PPCom`对话列表界面`里的某个客服组建立对话。

当客服管理员选择GROUP策略时，必须先在客服团队下创建一个`首选组`，并在`首选组`里添加一些客服。客服管理员可以建立多个客服组，PPCom会在对话列表界面显示这些客服组，用户可以单独和某一个客服组建立对话。

当用户用第一种方法建立对话时，系统会从`首选组`寻找在线且空闲的客服。如果找到符合条件的客服，则从中选取一个客服加入到这个对话中。否则就把`首选组`把所有的客服都加入到这个对话中。

当用户用第二种方法建立对话时，系统会从对应客服组寻找在线且空闲的客服。如果找到符合条件的客服，则从中选取一个客服加入到这个对话中。否则就把这个客服组里所有的客服都加入到这个对话中。
