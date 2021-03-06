# 自定义消息格式文档

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2021年04月07日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

自定义消息格式文档

## 产品说明

满足产品自定义展示消息

## 关键账户说明


| 用户ID | 身份  |
|:----:|:---:|
| 9999 | 通知 |
| 9998 | 用户通知 |
| 9997 | 官方小二 |



## 接口说明

自定义协议格式说明

``` json

		{
    "SyncOtherMachine": 1, //消息同步至发送方
    "From_Account": "10001",
    "To_Account": "10002",
    "MsgRandom": 1287657,
    "MsgTimeStamp": 5454457,
    "MsgBody": [
        {
            "MsgType": "TIMCustomElem", //自定义消息类型
            "MsgContent": {    
				     "type": 1,  //协议号 依次递增  具体格式参见下面协议定义
				     "version":"1.0", //协议版本号，本地配置目前能处理的版本号，高于该版本则提示需要升级识别		  
				     "tips":"消息会话列表显示提示",
				     "createTime": 1233434343l, //创建时间戳
				     "msg":{                    //消息体
				      "title":"标题", //标题
				      "url":"http://kistalk.com", // h5 广告页面
				      "content":"这是消息内容",
				      "imageUrl":"头图地址", //相对地址，自行追加
				      "coverWidth":300,  //高度
				      "coverHeight":400   //宽度
				      }
            }
        }
    ]
}
		
```



## 1000 通知消息

### 1001)  我的消息通知

#### 接口说明

| Type          | 1001             |
|:------------- |:-------------:|
| 版本号      |  1.0 |



####  协议说明


```json

      {    
			     "type": 1001,  //协议号 依次递增  具体格式参见下面协议定义
			     "version":"1.0", //协议版本号，本地配置目前能处理的版本号，高于该版本则提示需要升级识别	  
			     "tips":"消息会话列表显示提示",
			     "createTime": 1233434343l, //创建时间戳
			     "msg":{                    //文本消息
			         "uid":12345 , //发送人
			         "avatar":"xxxx" , //头像
			         "name":"名称" , //名称
			         "eventTime":123456789 , //直播时间
			         "eventType":1 , //事件类型 1 发起会议预约  2 发起会议直播 3 预约开始通知  4 好奇通知
			         "content":"名称" , //直播名称
			         "targetId":1, //对象ID 用于跳转
			      }
        }


```



### 1002)  与我相关协议

#### 接口说明

| Type          | 1002             |
|:------------- |:-------------:|
| 版本号      |  1.0 |



####  协议说明


```json

      {    
			     "type": 1002,  //协议号 依次递增  具体格式参见下面协议定义
			     "version":"1.0", //协议版本号，本地配置目前能处理的版本号，高于该版本则提示需要升级识别	  
			     "tips":"消息会话列表显示提示",
			     "createTime": 1233434343l, //创建时间戳
			     "msg":{  
			         "userList":[
			             {
			                 "uid":1,
			                 "avatar":"/a",
			                 "name":"xx"
			             }
			         ],
			         "eventType":1 , //事件类型 1 参与会议  2 一同参与会议 3 论文好奇  4  一同好奇
			         "content":"名称" , //直播名称
			         "targetId":1, //对象ID 用于跳转
			      }
        }


```


## 2000  通知


### 2001 )  举手状态变更通知

#### 接口说明

| Type          | 2001             |
|:------------- |:-------------:|
| 版本号      |  1.0 |
| 发送账号      |  9997 |
| 消息类型      |  群组消息 |



####  协议说明


```json

      {    
			     "type": 2001,  //协议号 依次递增  具体格式参见下面协议定义
			     "version":"1.0", //协议版本号，本地配置目前能处理的版本号，高于该版本则提示需要升级识别	  
			     "tips":"消息会话列表显示提示",
			     "createTime": 1233434343l, //创建时间戳
			     "msg":{  
                "meetingId": "xxxxxx" , //直播ID
			        "handStatus": 0, // 举手状态 0 放下 1 举手  -1 拒绝
			        "count":123, //举手人数  
			        "uid":123 //用户ID  
			      }
        }


```


### 2002 )  踢出用户通知

#### 接口说明

| Type          | 2002             |
|:------------- |:-------------:|
| 版本号      |  1.0 |
| 发送账号      |  9997 |
| 消息类型      |  群组消息 |



####  协议说明


```json

      {    
			     "type": 2002,  //协议号 依次递增  具体格式参见下面协议定义
			     "version":"1.0", //协议版本号，本地配置目前能处理的版本号，高于该版本则提示需要升级识别	  
			     "tips":"消息会话列表显示提示",
			     "createTime": 1233434343l, //创建时间戳
			     "msg":{  
                "meetingId": "xxxxxx" , //直播ID
			        "uid":123 //用户ID  
			      }
        }


```



### 2003 )  科学家认证结果通知

#### 接口说明

| Type          | 2003             |
|:------------- |:-------------:|
| 版本号      |  1.0 |
| 发送账号      |  9997 |
| 消息类型      | 个人消息 |



####  协议说明


```json

      {    
			     "type": 2003,  //协议号 依次递增  具体格式参见下面协议定义
			     "version":"1.0", //协议版本号，本地配置目前能处理的版本号，高于该版本则提示需要升级识别	  
			     "tips":"消息会话列表显示提示",
			     "createTime": 1233434343l, //创建时间戳
			     "msg":{  
                "status":  2 , //认证结果 2 通过 -1 驳回
			        "uid":123 //用户ID  
			      }
        }


```


