# 认证管理

[TOC]
## 修订记录
----

日期 | 作者 | 修订类型 | 修订内容 | 版本
---- | ---- | ---- | ---- | ---- |
2020年04月10日|冷立纲|A|新增设计方案|1.0

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

认证管理相关接口

## 产品说明


## 关键流程说明

## 接口说明


####  列表接口

##### 请求说明

| http 请求方式          | get |
|:------------- |:---------------:|
| url      |/admin/cert/list |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| page   | 否 | int  |  分页 |  |
| limit   | 否 | int  |  单页条数 |  |




#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "total": 19,
        "currentPage": 1,
        "list": [
            {
                "id": 73,
                "uid": 10415,
                "status": 2, //状态 2 通过 -1驳回 0 初始 1 待审核
                "imageUrl": "f09e82fa7b29254814cc8e0d90374b2c.png", //审核图片
                "addTime": 1622023224667, //添加时间
                "updateTime": 1622023255220,
                "auditType": "sys"
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": 2
    }
}
```



####  详情接口

##### 请求说明

| http 请求方式          | get|
|:------------- |:---------------:|
| url      |/admin/cert/read |


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
                "id": 73,
                "uid": 10415,
                "status": 2, //状态 2 通过 -1驳回 0 初始 1 待审核
                "imageUrl": "f09e82fa7b29254814cc8e0d90374b2c.png", //审核图片
                "addTime": 1622023224667, //添加时间
                "updateTime": 1622023255220,
                "auditType": "sys"
            }}

```




####  删除接口

##### 请求说明

| http 请求方式          | post |
|:------------- |:---------------:|
| url      |/admin/cert/delete |


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



####  审核接口

##### 请求说明

| http 请求方式          | post |
|:------------- |:---------------:|
| url      |/admin/cert/audit |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  ID | |
| status   | 是 | int  |  审核结果 | 2 通过 -1驳回 0 初始 1 待审核 |


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


