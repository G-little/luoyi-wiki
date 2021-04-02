# 话题相关接口

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

话题相关接口

## 产品说明



## 关键流程说明

## 接口说明



#### 1.0 话题用户列表

##### 接口说明

根据关键字查询学校列表

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/topic/user_list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| keyword      | 否| string  |  关键字 |   |
| page      | 否 | int  |  分页 |   |
| limit      | 否| int  |  单页条数 |  默认10 |
| type      | 是| int  |  标签类型 |   |
| tagId      | 是| int  |  标签ID |   |


#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "total": null,
        "currentPage": 1,
        "list": [
            {
                "uid": 10032,
                "avatar": "c1a1657a883f184d164954db82e2cbfd.png",
                "name": "陈破空",
                "workplace": "中国科学院广州生物医药与健康研究院",
                "jobTitle": null,
                "followStatus": 0
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}
```


#### 1.1 话题论文列表

##### 接口说明

根据关键字查询学校列表

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/topic/article_list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| keyword      | 否| string  |  关键字 |   |
| page      | 否 | int  |  分页 |   |
| limit      | 否| int  |  单页条数 |  默认10 |
| type      | 是| int  |  标签类型 |   |
| tagId      | 是| int  |  标签ID |   |


#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "total": null,
        "currentPage": 1,
        "list": [
            {
                "id": 1,
                "title": "Leaf form diversification in an heirloom tomato results from alterations in two different HOMEOBOX genes",
                "authors": [
                    "Hokuto Nakayama",
                    "Steven D. Rowland",
                    "Zizhang Cheng",
                    "Kristina Zumstein",
                    "Julie Kang",
                    "Yohei Kondo",
                    "Neelima R. Sinha"
                ],
                "visitorBrief": [
                    {
                        "nickname": null,
                        "avatar": null,
                        "uid": 10002,
                        "jobTitle": null
                    }
                ],
                "visitorCount": 1,
                "curiousCount": 0,
                "curious": true
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}
```



#### 1.2 会议列表

##### 接口说明

根据关键字查询学校列表

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/topic/meeting_list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| keyword      | 否| string  |  关键字 |   |
| page      | 否 | int  |  分页 |   |
| limit      | 否| int  |  单页条数 |  默认10 |
| type      | 是| int  |  标签类型 |   |
| tagId      | 是| int  |  标签ID |   |


#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "total": null,
        "currentPage": 1,
        "list": [
            {
                "id": 1,
                "type": 0,
                "content": "这是一次测试",
                "uid": 10002,
                "mayStartTime": 1616767200000,
                "orgId": null,
                "userLimit": 30,
                "startTime": null,
                "endTime": null,
                "subscribeCount": 0,
                "playUrl": null,
                "timeLen": null,
                "tags": null,
                "userBrief": [
                    {
                        "uid": 10002,
                        "avatar": null,
                        "name": null,
                        "workplace": null,
                        "jobTitle": null,
                        "meetingRole": 1
                    }
                ],
                "status": 1,
                "privacyLevel": "public"
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}
```








