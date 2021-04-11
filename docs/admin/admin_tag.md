# 标签管理

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
| url      |/admin/tags/list |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 否 | int  |  标签类型 |  1 学科标签 2 细分领域标签 3 其他 |
| page   | 否 | int  |  分页 |  |
| limit   | 否 | int  |  单页条数 |  |




#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "total": 195,
        "currentPage": 1,
        "list": [
            {
                "id": 197,
                "type": 2,
                "value": "物理",
                "brief": null, //简介
                "addTime": null
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": 20
    }
}

```


####  添加接口

##### 请求说明

| http 请求方式          | post json |
|:------------- |:---------------:|
| url      |/admin/tags/create |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 否 | int  |  标签类型 |  1 学科标签 2 细分领域标签 3 其他 |
| value   | 是 | string  |   标签名 |  |
| brief   | 否 | string  |  标签简介 |  |


##### 请求实例

```json

{
    "type":3,
    "value":"测试",
    "brief":"这是一条测试"
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
| url      |/admin/tags/read |


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
        "id": 198,
        "type": 3,
        "value": "测试",
        "brief": "这是一条测试",
        "addTime": null
    }
}

```


####  更新接口

##### 请求说明

| http 请求方式          | post json |
|:------------- |:---------------:|
| url      |/admin/tags/update |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  ID | |
| type   | 否 | int  |  标签类型 |  1 学科标签 2 细分领域标签 3 其他 |
| value   | 是 | string  |   标签名 |  |
| brief   | 否 | string  |  标签简介 |  |


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
    "c": 0,
    "m": null,
    "d": {
        "id": 198,
        "type": 3,
        "value": "测试",
        "brief": "这是一条测试2"
    }
}

```



####  删除接口

##### 请求说明

| http 请求方式          | post |
|:------------- |:---------------:|
| url      |/admin/tags/delete |


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
