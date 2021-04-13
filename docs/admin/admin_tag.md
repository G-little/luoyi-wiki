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



####  相关用户接口

##### 请求说明

| http 请求方式          | get |
|:------------- |:---------------:|
| url      |/admin/tags/related_user |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 否 | int  |  标签类型 |  1 学科标签 2 细分领域标签 3 其他 |
| tagId   | 否 | int  |  标签ID |  标签ID |
| page   | 否 | int  |  分页 |  |
| limit   | 否 | int  |  单页条数 |  |




#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 1,
        "total": null,
        "currentPage": 1,
        "list": [
            {
                "uid": 10066,
                "avatar": "image/202104/0c30b55b7386aafe4517082c7f0b4318.jpg",
                "name": "0012",
                "gender": -1,
                "birthday": null,
                "status": 0,
                "mobile": "12112340012",
                "createTime": 1618214018456,
                "updateTime": 1618214106808,
                "userRole": null,
                "certStatus": null,
                "workplace": "美国Celgene公司",
                "studySubject": "生物学",
                "subjectField": "基因组学",
                "jobTitle": null,
                "realName": null,
                "tags": [
                    {
                        "type": 1,
                        "tagId": 1,
                        "value": "生物学"
                    },
                    {
                        "type": 2,
                        "tagId": 15,
                        "value": "基因组学"
                    }
                ],
                "userType": null,
                "subjectId": null,
                "fieldId": null,
                "email": null
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}
```




####  相关论文接口

##### 请求说明

| http 请求方式          | get |
|:------------- |:---------------:|
| url      |/admin/tags/related_article |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 否 | int  |  标签类型 |  1 学科标签 2 细分领域标签 3 其他 |
| tagId   | 否 | int  |  标签ID |  标签ID |
| page   | 否 | int  |  分页 |  |
| limit   | 否 | int  |  单页条数 |  |




#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 1,
        "total": null,
        "currentPage": 1,
        "list": [
            {
                "id": 1,
                "subjects": "3",
                "doi": "https://doi.org/10.1101/2020.09.08.287011",
                "postDate": 1599580800,
                "pdfUrl": "https://www.biorxiv.org/content/10.1101/2020.09.08.287011v1.full.pdf",
                "externalId": "10.1101/2020.09.08.287011v1",
                "isNormal": 1,
                "createTime": 1608889848,
                "updateTime": null,
                "source": "biorxiv",
                "isAuthentication": true,
                "status": true,
                "banReason": null,
                "contactAuthor": null,
                "contactAddress": null,
                "contactEmail": null,
                "scholarId": null,
                "adminId": null,
                "operateIp": null,
                "showId": "ac73740a2654b8ffc1c090fca04b6d86",
                "title": "<h1 class=\"highwire-cite-title\" id=\"page-title\">Leaf form diversification in an heirloom tomato results from alterations in two different <em>HOMEOBOX</em> genes</h1>",
                "authors": "1,2,3,4,5,6,7",
                "subjectsNumber": null,
                "keys": null,
                "brief": "<div class=\"section abstract\" id=\"abstract-1\"><p id=\"p-4\">Domesticated plants and animals display tremendous diversity in various phenotypic traits and often this diversity is seen within the same species. Tomato (<em>Solanum lycopersicum</em>; Solanaceae) cultivars show wide variation in leaf morphology, but the influence of breeding efforts in sculpting this diversity is not known. Here, we demonstrate that a single nucleotide deletion in the homeobox motif of <em>BIPINNATA</em>, which is a <em>BEL-LIKE HOMEODOMAIN</em> gene, led to a highly complex leaf phenotype in an heirloom tomato, Silvery Fir Tree (SiFT). Additionally, a comparative gene network analysis revealed that reduced expression of the ortholog of <em>WUSCHEL RELATED HOMEOBOX 1</em> is also important for the narrow leaflet phenotype seen in SiFT. Phylogenetic and comparative genome analysis using whole-genome sequencing data suggests that the <em>bip</em> mutation in SiFT is likely a <em>de novo</em> mutation, instead of standing genetic variation. These results provide new insights into natural variation in phenotypic traits introduced into crops during improvement processes after domestication.</p></div>",
                "url": "https://www.biorxiv.org/content/10.1101/2020.09.08.287011v1"
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}
```




####  相关会议

##### 请求说明

| http 请求方式          | get |
|:------------- |:---------------:|
| url      |/admin/tags/related_meeting |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 否 | int  |  标签类型 |  1 学科标签 2 细分领域标签 3 其他 |
| tagId   | 否 | int  |  标签ID |  标签ID |
| page   | 否 | int  |  分页 |  |
| limit   | 否 | int  |  单页条数 |  |




#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 1,
        "total": null,
        "currentPage": 1,
        "list": [
            {
                "id": 352,
                "streamId": null,
                "type": 1,
                "content": "在。嗯",
                "uid": 10007,
                "verifyCode": null,
                "mayStartTime": null,
                "orgId": null,
                "userLimit": 30,
                "startTime": 1618283409403,
                "endTime": 1618283511972,
                "deleted": false,
                "addTime": 1618283408482,
                "subscribeCount": 0,
                "notifyStatus": 0,
                "playUrl": null,
                "timeLen": null,
                "tags": [
                    {
                        "type": 1,
                        "tagId": 145,
                        "value": "医学"
                    },
                    {
                        "type": 2,
                        "tagId": 196,
                        "value": "泌尿学"
                    }
                ],
                "userBrief": [
                    {
                        "uid": 10007,
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
        "totalPage": null
    }
}

```



####  添加相关

##### 请求说明

| http 请求方式          | post |
|:------------- |:---------------:|
| url      |/admin/tags/add_entity |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| tagType   | 否 | int  |  标签类型 |  1 学科标签 2 细分领域标签 3 其他 |
| tagId   | 否 | int  |  标签ID |  标签ID |
| entityType   | 否 | int  |  ID类别 | 3:论文 2:会议 1：用户  |
| entityId   | 否 | int  |  单页条数 |  |




#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
    
    }
}

```



####  添加相关

##### 请求说明

| http 请求方式          | post |
|:------------- |:---------------:|
| url      |/admin/tags/remove_entity |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| tagType   | 否 | int  |  标签类型 |  1 学科标签 2 细分领域标签 3 其他 |
| tagId   | 否 | int  |  标签ID |  标签ID |
| entityType   | 否 | int  |  ID类别 | 3:论文 2:会议 1：用户  |
| entityId   | 否 | int  |  单页条数 |  |




#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
    
    }
}

```


