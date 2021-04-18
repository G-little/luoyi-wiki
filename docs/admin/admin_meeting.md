# 会议管理

[TOC]
## 修订记录
----

日期 | 作者 | 修订类型 | 修订内容 | 版本
---- | ---- | ---- | ---- | ---- |
2020年04月10日|冷立纲|A|新增设计方案|1.0

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

会议管理相关接口

## 产品说明


## 关键流程说明

## 接口说明


####  列表接口

##### 请求说明

| http 请求方式          | get |
|:------------- |:---------------:|
| url      |/admin/meeting/list |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 否 | int  |  直播ID |   |
| name   | 否 | string  | 姓名 |   |
| status   | 否 | int  | 直播状态 | 0 空闲  -1 结束 -2 删除 1 直播中   |
| startTime   | 否 | string  | 时间范围筛选 | |
| endTime   | 否 | string  | 时间范围筛选  | |
| page   | 否 | int  |  分页 |  |
| limit   | 否 | int  |  单页条数 |  |




#####  返回实例

```

 {
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 1,
        "total": 142,
        "currentPage": 1,
        "list": [
            {
                "id": 331,
                "streamId": null,
                "type": 0,
                "content": "迷不知返",
                "uid": 10024,
                "verifyCode": null,
                "mayStartTime": null,
                "orgId": null,
                "userLimit": 30,
                "startTime": 1618212405928,
                "endTime": 1618212670498,
                "deleted": false,
                "addTime": 1618212404267,
                "subscribeCount": 0,
                "notifyStatus": 0,
                "playUrl": null,
                "timeLen": null,
                "tags": null,
                "userBrief": [
                    {
                        "uid": 10024,
                        "role": 1
                    }
                ],
                "status": -1,
                "privacyLevel": "public",
                "save": false,
                "coverUrl": null,
                "coverSize": null
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": 142
    }
}

```



####  创建接口

##### 请求说明

| http 请求方式          | post json |
|:------------- |:---------------:|
| url      |/admin/meeting/create |


#####  输入参数

__meeting参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 是 | int  |  类型 | 0 音频 1 视频  |
| content   | 是 | string  |   标题 |  |
| uid   | 是 | int  |  创建人 |   |
| verifyCode   | 否 | String  |  验证码 |   |
| mayStartTime   | 是 | String  |  预计开始时间 |  yyyy-MM-dd HH:mm:ss  |
| userLimit   | 否 | int  |  限制人数 |  |
| status   | 否 | int  |  直播状态 |  0:空闲 -1:结束 -2:删除 1:直播中  |
| save   | 否 | boolean  |  是否录制 |   |
| coverUrl   | 否 | string  |  封面 |   |
| coverSize   | 否 | string  | 封面尺寸 `x*y` |   |
| spearkerArray   | 是 | int[]  |  主播 |   |
| tags   | 否 | json  |   标签 |  |
| relatedList   | 否 | json[]  |   相关 |  |

__tags参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 是 | int  |  标签类型 |  1 学科 2 细分领域 3 其他    |
| tagId   | 是 | int  |   标签ID |  |
| value   | 是 | string  |   标签值 |  |


__relatedList参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| name   | 是 | string  |  字段名称 |     |
| value   | 是 | string  |   字段值 |  |
| type   | 是 | int  | 类型  | 1 相关论文 2相关技术  3相关人物 4 相关院校  |
| targetId   | 否 | int  | 关联ID  |  |



##### 请求实例

```json

{
        "id": 1,
        "type": 0,
        "content": "这是一次测试",
        "uid": 10002,
        "verifyCode": "xxxxxx",
        "mayStartTime": "2021-04-12 18:00",
        "orgId": null,
        "userLimit": 30,
        
        "status": -1,
        "privacyLevel": "public",
        "save": false,
        "coverUrl": "/b",
        "coverSize": "300*300",
        "spearkerArray":[10002,10003]
    }


```


#####  返回实例

```
 {
    "c": 0,
    "m": null,
    "d": {

    }
}
```




####  详情接口

##### 请求说明

| http 请求方式          | get|
|:------------- |:---------------:|
| url      |/admin/meeting/read |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  ID |  |



#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "meetingDTO": {
            "id": 2,
            "streamId": null,
            "type": 0,
            "content": "测试",
            "uid": 10024,
            "verifyCode": "123456",
            "mayStartTime": 1617352740000,
            "orgId": null,
            "userLimit": 30,
            "startTime": 1617351450940,
            "endTime": 1617352500098,
            "deleted": false,
            "addTime": 1617345589809,
            "subscribeCount": 0,
            "notifyStatus": 0,
            "playUrl": null,
            "timeLen": null,
            "tags": null,
            "userBrief": [
                {
                    "uid": 10024,
                    "role": 1
                }
            ],
            "status": -1,
            "privacyLevel": "private",
            "save": false,
            "coverUrl": null,
            "coverSize": null
        },
        "userBrief": {
            "uid": 10024,
            "fansCount": 4,
            "followCount": 1,
            "meetingCount": 0,
            "joinMeetingCount": 0,
            "curiousCount": 0,
            "addTime": 1617799692605
        },
        "relatedList": []
    }
}


```


####  更新接口

##### 请求说明

| http 请求方式          | post json |
|:------------- |:---------------:|
| url      |/admin/meeting/update |


#####  输入参数

__meeting参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  会议ID |  |
| type   | 是 | int  |  类型 | 0 音频 1 视频  |
| content   | 是 | string  |   标题 |  |
| uid   | 是 | int  |  创建人 |   |
| verifyCode   | 否 | String  |  验证码 |   |
| mayStartTime   | 是 | String  |  预计开始时间 |  yyyy-MM-dd HH:mm:ss  |
| userLimit   | 否 | int  |  限制人数 |  |
| status   | 否 | int  |  直播状态 |  0:空闲 -1:结束 -2:删除 1:直播中  |
| save   | 否 | boolean  |  是否录制 |   |
| coverUrl   | 否 | string  |  封面 |   |
| coverSize   | 否 | string  | 封面尺寸 `x*y` |   |
| tags   | 否 | json  |   标签 |  |
| relatedList   | 否 | []json   |   相关数据 |  |

__tags参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 是 | int  |  标签类型 |  1 学科 2 细分领域 3 其他    |
| tagId   | 是 | int  |   标签ID |  |
| value   | 是 | string  |   标签值 |  |



__relatedList参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| name   | 是 | string  |  名称 |     |
| value   | 是 | string  |   值 |  |
| type   | 是 | int  |   类型 |  1 论文 2 技术 3 人物 4 院校 |
| targetId   | 否 | int  |   类型 |   关联ID |



##### 请求实例

```json

{
    "c": 0,
    "m": null,
    "d": {
        "id": 1,
        "type": 0,
        "content": "这是一次测试",
        "uid": 10002,
        "verifyCode": "xxxxxx",
        "mayStartTime": "2021-04-12 18:00",
        "orgId": null,
        "userLimit": 30,
        "deleted": null,
        "tags": null,
        "spearkerArray": [
            10002,
            10003
        ],
        "privacyLevel": "public",
        "save": false,
        "relatedList":[{
            "name":"名称",
            "value":"值",
            "type":"类型"
        }]
    }
}


```


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "id": 1,
        "type": 0,
        "content": "这是一次测试",
        "uid": 10002,
        "verifyCode": "xxxxxx",
        "mayStartTime": "2021-04-12 18:00",
        "orgId": null,
        "userLimit": 30,
        "deleted": null,
        "tags": null,
        "spearkerArray": [
            10002,
            10003
        ],
        "privacyLevel": "public",
        "save": false
    }
}

```



####  删除接口

##### 请求说明

| http 请求方式          | post |
|:------------- |:---------------:|
| url      |/admin/meeting/delete |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  ID | |


##### 请求实例

```json

{
    "id":198,
}


```


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
    }
}

```




####  评论列表接口

##### 请求说明

| http 请求方式          | get  |
|:------------- |:---------------:|
| url      |/admin/meeting/list |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  ID | 会议ID |
| page   | 否 | int  |  分页 | |
| limit   | 否 | int  |  单页条数 | |


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 20,
        "total": null,
        "currentPage": 1,
        "list": [
            {
                "id": 1,
                "meetingId": 168,
                "uid": 10032,
                "msg": "send group message success.",
                "addTime": 1617955392742,
                "name": "陈破空"
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}

```


####  踢出用户

##### 请求说明

| http 请求方式          | put  |
|:------------- |:---------------:|
| url      |/admin/meeting/kickout_user |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| meetingId   | 是 | int  | 会议ID  |  |
| uid   | 是 | int  | 用户ID  |  |





#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
    
    }
}

```



####  发消息

##### 请求说明

| http 请求方式          | post  |
|:------------- |:---------------:|
| url      |/admin/meeting/send_msg |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| meetingId   | 是 | int  | 会议ID  |  |
| msg   | 是 |  string | 内容  |  |


#####  请求实例

```

{
    "meetingId":123,
    "msg":"haha"
}

```


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "id":12345 //消息ID
    }
}

```




####  删除消息

##### 请求说明

| http 请求方式          | post  |
|:------------- |:---------------:|
| url      |/admin/meeting/del_msg |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| msgId   | 是 | int  | 消息ID  |  |


#####  请求实例

```

{
    "msgId":123
}

```


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
      
    }
}

```

