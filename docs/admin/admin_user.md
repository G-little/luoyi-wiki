# 用户管理

[TOC]
## 修订记录
----

日期 | 作者 | 修订类型 | 修订内容 | 版本
---- | ---- | ---- | ---- | ---- |
2020年04月10日|冷立纲|A|新增设计方案|1.0

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

标签管理相关接口

## 产品说明


## 关键流程说明

## 接口说明


####  列表接口

##### 请求说明

| http 请求方式          | get |
|:------------- |:---------------:|
| url      |/admin/user/list |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| mobile   | 否 | string  |  手机号 |   |
| name   | 否 | string  |  昵称 |   |
| gender   | 否 | int  |  性别 |  1:男 -1:女 0:保密  |
| workplace   | 否 | string  |  学校/单位 |   |
| studySubject   | 否 | string  |  学科 |   |
| subjectField   | 否 | string  |  细分领域 |   |
| startTime   | 否 | string  |  注册时间 | 开始时间  yyyy-MM-dd HH:mm:ss  |
| endTime   | 否 | string  |  注册时间 | 结束时间   |
| page   | 否 | int  |  分页 |  |
| limit   | 否 | int  |  单页条数 |  |



#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 1,
        "total": 62,
        "currentPage": 1,
        "list": [
            {
                "uid": 10062,
                "avatar": "image/202104/e1f0ab0223e6c354003962b303cd3ce8.jpg",
                "name": "高潭清",
                "gender": -1,
                "birthday": null,
                "status": 0,
                "mobile": "18624491285",
                "createTime": 1617982758165,
                "updateTime": 1617983142034,
                "userRole": null,
                "certStatus": null,
                "workplace": "美团",
                "studySubject": "医学",
                "subjectField": "毒理学",
                "jobTitle": null,
                "realName": null,
                "tags": [
                    {
                        "type": 1,
                        "tagId": 145,
                        "value": "医学"
                    },
                    {
                        "type": 2,
                        "tagId": 194,
                        "value": "毒理学"
                    }
                ],
                "userType": null,
                "email": null
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": 62
    }
}

```


####  添加接口

##### 请求说明

| http 请求方式          | post json |
|:------------- |:---------------:|
| url      |/admin/user/create |


#####  输入参数

__user参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| avatar   | 是 | string  |  头像 |   |
| name   | 是 | string  |   昵称|  |
| gender   | 是 | int  |  性别 | -1:女 0:保密 1:男  |
| status   | 否 | int  |  状态 |  0 正常  -1 禁止 |
| mobile   | 是 | string  |  手机号  | |
| workplace   | 否 | string  |  单位/学校 | |
| studySubject   | 否 | string  |  学科 | |
| subjectField   | 否 | string  |  细分领域 | |
| jobTitle   | 否 | string  |  头衔 | |
| tags   | 否 | json  |  标签 | |

__tags参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 是 | int  |  标签类型 |  1 学科 2 细分领域 3 其他    |
| tagId   | 是 | int  |   标签ID |  |
| value   | 是 | string  |   标签值 |  |



##### 请求实例

```json

{
    "avatar": "image/202104/e1f0ab0223e6c354003962b303cd3ce8.jpg",
    "name": "高潭清",
    "gender": -1,
    "status": 0,
    "mobile": "15201008999",
    "workplace": "美团",
    "studySubject": "医学",
    "subjectField": "毒理学",
    "jobTitle": null,
    "realName": null,
    "tags": [
        {
            "type": 1,
            "tagId": 145,
            "value": "医学"
        },
        {
            "type": 2,
            "tagId": 194,
            "value": "毒理学"
        }
    ],
    "userType": 1,
    "email": null
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
| url      |/admin/user/read |


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
        "uid": 10063,
        "avatar": "image/202104/e1f0ab0223e6c354003962b303cd3ce8.jpg",
        "name": "高潭清",
        "gender": -1,
        "birthday": null,
        "status": 0,
        "mobile": "15201008999",
        "createTime": 1618058530475,
        "updateTime": null,
        "userRole": null,
        "certStatus": null,
        "workplace": "美团",
        "studySubject": "医学",
        "subjectField": "毒理学",
        "jobTitle": null,
        "realName": null,
        "tags": [
            {
                "type": 1,
                "tagId": 145,
                "value": "医学"
            },
            {
                "type": 2,
                "tagId": 194,
                "value": "毒理学"
            }
        ],
        "userType": 1,
        "email": null
    }
}
```


####  更新接口

##### 请求说明

| http 请求方式          | post json |
|:------------- |:---------------:|
| url      |/admin/user/update |


#####  输入参数

__user参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| uid   | 是 | int  |  用户ID |   |
| avatar   | 是 | string  |  头像 |   |
| name   | 是 | string  |   昵称|  |
| gender   | 是 | int  |  性别 | -1:女 0:保密 1:男  |
| status   | 否 | int  |  状态 |  0 正常  -1 禁止 |
| mobile   | 是 | string  |  手机号  | |
| workplace   | 否 | string  |  单位/学校 | |
| studySubject   | 否 | string  |  学科 | |
| subjectField   | 否 | string  |  细分领域 | |
| jobTitle   | 否 | string  |  头衔 | |
| tags   | 否 | json  |  标签 | |

__tags参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 是 | int  |  标签类型 |  1 学科 2 细分领域 3 其他    |
| tagId   | 是 | int  |   标签ID |  |
| value   | 是 | string  |   标签值 |  |


##### 请求实例

```json

{
    "c": 0,
    "m": null,
    "d": {
        "uid": 10063,
        "avatar": "image/202104/e1f0ab0223e6c354003962b303cd3ce8.jpg",
        "name": "高潭清",
        "gender": -1,
        "birthday": null,
        "status": 0,
        "mobile": "15201008999",
        "createTime": 1618058530475,
        "updateTime": null,
        "userRole": null,
        "certStatus": null,
        "workplace": "美团",
        "studySubject": "医学",
        "subjectField": "毒理学",
        "jobTitle": null,
        "realName": null,
        "tags": [
            {
                "type": 1,
                "tagId": 145,
                "value": "医学"
            },
            {
                "type": 2,
                "tagId": 194,
                "value": "毒理学"
            }
        ],
        "userType": 1,
        "email": null
    }
}



```


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "uid": 10063,
        "avatar": "image/202104/e1f0ab0223e6c354003962b303cd3ce8.jpg",
        "name": "高潭清",
        "gender": -1,
        "birthday": null,
        "status": 0,
        "mobile": "15201008999",
        "createTime": 1618058530475,
        "updateTime": null,
        "userRole": null,
        "certStatus": null,
        "workplace": "美团",
        "studySubject": "医学",
        "subjectField": "毒理学",
        "jobTitle": null,
        "realName": null,
        "tags": [
            {
                "type": 1,
                "tagId": 145,
                "value": "医学"
            },
            {
                "type": 2,
                "tagId": 194,
                "value": "毒理学"
            }
        ],
        "userType": 1,
        "email": null
    }
}

```



####  删除接口

##### 请求说明

| http 请求方式          | post |
|:------------- |:---------------:|
| url      |/admin/user/delete |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| uid   | 是 | int  |  ID | |


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

