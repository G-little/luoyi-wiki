# 专辑管理

[TOC]
## 修订记录
----

日期 | 作者 | 修订类型 | 修订内容 | 版本
---- | ---- | ---- | ---- | ---- |
2020年04月10日|冷立纲|A|新增设计方案|1.0

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

专辑管理相关接口

## 产品说明


## 关键流程说明

## 接口说明


####  列表接口

##### 请求说明

| http 请求方式          | get |
|:------------- |:---------------:|
| url      |/admin/album/list |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderBy   | 否 | string  |  排序 |  add_time:添加时间/sort_field:排序字段  |
| keyword   | 否 | string  |  搜索字 |  |
| page   | 否 | int  |  分页 |  |
| limit   | 否 | int  |  单页条数 |  |




#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "total": 1,
        "currentPage": 1,
        "list": [
            {
                "id": 1, //ID
                "title": "test",//标题
                "brief": "test", //简介
                "imageUrl": "/test", //封面
                "sortField": null, //排序字段
                "userCount": 1, //用户数
                "addTime": null, //添加时间
                "deleted": false //删除状态
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0,
        "totalPage": 1
    }
}

```


####  添加专辑

##### 请求说明

| http 请求方式          | post json |
|:------------- |:---------------:|
| url      |/admin/album/create |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| title   | 是 | string  |  标题| |
| brief   | 是 | string  |  简介 |  |
| imageUrl   | 是 | string  |  封面 |  |
| itemList   | 否 | int[]  | 数组 | 科学家UID数组  |


##### 请求实例

```json

{
    "title": "最有前途科学家TOP 1",
    "brief": "最有前途科学家TOP 1",
    "imageUrl": "/test",
    "sortField": null,
    "userCount": 1,
    "itemList":[10314]
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
| url      |/admin/album/read |


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
        "id": 2,
        "title": "最有前途科学家TOP 1",
        "brief": "最有前途科学家TOP 1",
        "imageUrl": "/test",
        "sortField": null,
        "userCount": 1,
        "addTime": null,
        "deleted": false,
        "itemList": [
            {
                "id": 2,
                "albumId": 2, //专辑ID
                "uid": 10314, //用户ID
                "addTime": 1622020070352 //添加时间
            }
        ]
    }
}

```


####  更新接口

##### 请求说明

| http 请求方式          | post json |
|:------------- |:---------------:|
| url      |/admin/album/update |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  ID| |
| title   | 是 | string  |  标题| |
| brief   | 是 | string  |  简介 |  |
| imageUrl   | 是 | string  |  封面 |  |
| itemList   | 否 | int[]  | 数组 | 科学家UID数组  |

##### 请求实例

```json

{
    "id":198,
    "type":3,
    "value":"测试",
    "brief":"这是一条测试2"
}


```


#####  返回实例

```

{
    "id":3,
    "title": "最有前途科学家TOP 1",
    "brief": "最有前途科学家TOP 1",
    "imageUrl": "/test",
    "sortField": null,
    "userCount": 1,
    "itemList":[10314]
}


```



####  删除接口

##### 请求说明

| http 请求方式          | post |
|:------------- |:---------------:|
| url      |/admin/album/delete |


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



