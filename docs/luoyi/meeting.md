# 论文相关接口

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

论文相关接口

## 产品说明



## 关键流程说明

## 接口说明



#### 1.0 论文列表

##### 接口说明

创建会议

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/article/list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| subjectType      | 否| int  |  论文类型 |    |
| keyword      | 否| string  |  关键字 |    |
| page      | 否| int  |  页码 |    |
| limit      | 否| int  |  单页条数 |    |


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
                "visitorBrief": null,
                "visitorCount": 0,
                "curiousCount": 0
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}

```



