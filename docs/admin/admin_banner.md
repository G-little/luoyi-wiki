# 广告位管理

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
| url      |/admin/banner/list |


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
        "total": 1,
        "currentPage": 1,
        "list": [
            {
                "id": 3,
                "title": "测试1", //标题
                "type": 1, //类型 1:会议详情页，2:论文详情页，3:个人主页，4:站外跳转url
                "imageUrl": "lk2uyn05rdo7fvstyram.jpg",
                "enabled": true, //是否启用
                "deleted": false, //是否已删除
                "createTime": null, //创建时间
                "linkId": 100004, //关联ID
                "url": null //关联URL
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
| url      |/admin/banner/create |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| title   | 是 | string  |  标题| |
| type   | 是 | 类型  |  类型  | 1:会议详情页，2:论文详情页，3:个人主页，4:站外跳转url  |
| enabled   | 是 | boolean  |  是否开启 |  |
| linkId   | 是 | int  | 关联ID |  |
| url   | 否 | string  | 站外url |  |


##### 请求实例

```json

{
    "title": "测试6",
    "type": 1,
    "imageUrl": "lk2uyn05rdo7fvstyram.jpg",
    "enabled": true,
    "deleted": false,
    "createTime": null,
    "linkId": 100004,
    "url": null
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
| url      |/admin/banner/read |


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
        "id": 1,
        "title": "论文详情页",
        "type": 2,
        "imageUrl": "7nu9ceooo1si4x500gtj.png",
        "enabled": true,
        "deleted": false,
        "createTime": null,
        "linkId": 3,
        "url": null
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
| type   | 是 | 类型  |  类型  | 1:会议详情页，2:论文详情页，3:个人主页，4:站外跳转url  |
| enabled   | 是 | boolean  |  是否开启 |  |
| linkId   | 是 | int  | 关联ID |  |
| url   | 否 | string  | 站外url |  |

##### 请求实例

```json

{
    "id":7,
    "title": "测试6",
    "type": 1,
    "imageUrl": "lk2uyn05rdo7fvstyram.jpg",
    "enabled": true,
    "deleted": false,
    "createTime": null,
    "linkId": 100004,
    "url": null
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



