# 搜索相关接口

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

搜索相关接口

## 产品说明



## 关键流程说明

## 接口说明



#### 1.0 联想接口

##### 接口说明

根据关键字查询学校列表

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/search/guess |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| keyword      | 否| string  |  关键字 |   |


#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": [
        {
            "type": 1,  // 1 人  2 会议 3 论文 4 tag（tag 会返回tagType）
            "id": 12345,
            "title": "陈破空",
            "highlightField": [
                "|陈|破空"
            ] // | 线分割高亮
        }
    ]
}
```


#### 1.1 搜索接口 

##### 接口说明

根据关键字搜索

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/search/index |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| keyword      | 否| string  |  关键字 |   |
| page      | 否 | int  |  分页 |   |
| limit      | 否| int  |  单页条数 |  默认10 |
| type      | 是| int  |  查询类别 |  1 用户 2 会议 3 论文 4标签  |


#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "userPage": {
            "pageSize": 2,
            "total": 2,
            "currentPage": 1,
            "list": [
                {
                    "uid": 10031,
                    "avatar": "606596041253C53739C37FFE",
                    "name": "陈破空",
                    "workplace": "德国IFW研究所",
                    "jobTitle": null,
                    "followStatus": 0,
                    "fansCount":100,
                    "followCount":100,
                }
            ],
            "end": false,
            "empty": false,
            "startIndex": 0,
            "totalPage": 1
        },
        "meetingPage": {
            "pageSize": 2,
            "total": 0,
            "currentPage": 1,
            "list": [
                {
                    "id": 19,
                    "type": 1,
                    "content": "给哥哥",
                    "uid": 10032,
                    "mayStartTime": 1617386460000,
                    "orgId": null,
                    "userLimit": 30,
                    "startTime": 1617361283366,
                    "endTime": null,
                    "subscribeCount": 0,
                    "playUrl": null,
                    "timeLen": null,
                    "tags": [
                        {
                            "type": 1,
                            "tagId": 1,
                            "value": "生物学"
                        },
                        {
                            "type": 2,
                            "tagId": 26,
                            "value": "合成生物学"
                        }
                    ],
                    "userBrief": [
                        {
                            "uid": 10032,
                            "avatar": "c1a1657a883f184d164954db82e2cbfd.png",
                            "name": "陈破空",
                            "workplace": null,
                            "jobTitle": null,
                            "meetingRole": 1
                        }
                    ],
                    "status": -1,
                    "privacyLevel": "public",
                    "subscribed": false
                }
            ],
            "end": true,
            "empty": true,
            "startIndex": 0,
            "totalPage": 0
        },
        "articlePage": {
            "pageSize": 2,
            "total": 0,
            "currentPage": 1,
            "list": [
                 {
                    "id": 1577006,
                    "title": "Ha Emission from the Magellanic Bridge",
                    "authors": [
                        "Q. Parker",
                        "E. Muller"
                    ],
                    "visitorBrief": null,
                    "visitorCount": 0,
                    "curiousCount": 0,
                    "curious": false
                }
            ],
            "end": true,
            "empty": true,
            "startIndex": 0,
            "totalPage": 0
        },
        "tagPage": {
            "pageSize": 2,
            "total": 0,
            "currentPage": 1,
            "list": [
                {
                    "id": 1,
                    "type": 1,
                    "value": "测试一下",
                    "addTime": null
                }
            ],
            "end": true,
            "empty": true,
            "startIndex": 0,
            "totalPage": 0
        }
    }
}
```











