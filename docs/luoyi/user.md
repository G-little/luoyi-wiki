# 个人信息相关接口

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



#### 1.1 个人主页

##### 接口说明

创建会议

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/home/index |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| uid      | 否| int  |  用户ID |    |
| type      | 否| int  |  事件类型 |  null 全部，1 好奇  2 主讲 3 参加   |
| page      | 否| int  |  页码 |  分页  |
| limit      | 否| int  |  单页条数 |  单页条数  |


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
                "id": 2, //好奇
                "uid": 10002,
                "addTime": null,
                "type": 1,
                "targetId": 1,
                "ext": {
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
                    "brief": "Domesticated plants and animals display tremendous diversity in various phenotypic traits and often this diversity is seen within the same species. Tomato (Solanum lycopersicum; Solanaceae) cultivars show wide variation in leaf morphology, but the influence of breeding efforts in sculpting this diversity is not known. Here, we demonstrate that a single nucleotide deletion in the homeobox motif of BIPINNATA, which is a BEL-LIKE HOMEODOMAIN gene, led to a highly complex leaf phenotype in an heirloom tomato, Silvery Fir Tree (SiFT). Additionally, a comparative gene network analysis revealed that reduced expression of the ortholog of WUSCHEL RELATED HOMEOBOX 1 is also important for the narrow leaflet phenotype seen in SiFT. Phylogenetic and comparative genome analysis using whole-genome sequencing data suggests that the bip mutation in SiFT is likely a de novo mutation, instead of standing genetic variation. These results provide new insights into natural variation in phenotypic traits introduced into crops during improvement processes after domestication."
                },
                "followStatus": null
            },
            {
                "id": 1,  //会议
                "uid": 10002,
                "addTime": null,
                "type": 3,
                "targetId": 1,
                "ext": {
                    "type": 0,
                    "meetingId": 1,
                    "coverUrl": "",
                    "title": "这是一次测试",
                    "userBrief": [
                        {
                            "uid": 10002,
                            "avatar": null,
                            "name": null,
                            "jobTitle": null,
                            "meetingRole": 1
                        }
                    ]
                },
                "followStatus": 0
            }
        ],
        "end": true,
        "user": {
            "uid": 10002,
            "avatar": null,
            "name": null,
            "jobTitle": null,
            "workplace": null,
            "fansCount": 0,
            "followCount": 0,
            "meetingCount": 0,
            "joinMeetingCount": 0,
            "curiousCount": 0,
            "tags": []
        },
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}

```



#### 1.2 查询用户信息

##### 接口说明

创建会议

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/u/list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| uidArray      | 是| int[]  |  用户ID数组 |    |


#####  错误说明





#####  返回实例
```json

{
    "c": 0,
    "m": null,
    "d": [
        {
            "uid": 10001,
            "avatar": null,
            "name": null,
            "workplace": null,
            "jobTitle": null,
            "followStatus": 0,
            "fansCount": null,
            "followCount": null
        },
        {
            "uid": 10002,
            "avatar": null,
            "name": null,
            "workplace": null,
            "jobTitle": null,
            "followStatus": 0,
            "fansCount": 0,
            "followCount": 1
        }
    ]
}
```




#### 1.3 机构号列表

##### 接口说明

创建会议

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/u/org_list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| page      | 否 | int  |   |    分页 |
| limit      | 否 | int  |   |  分页条数  |


#####  错误说明





#####  返回实例
```json

{
    "c": 0,
    "m": null,
    "d": [
        {
            "uid": 10001,
            "avatar": null,
            "name": null,
            "workplace": null,
            "jobTitle": null,
            "followStatus": 0
        }
    ]
}
```



