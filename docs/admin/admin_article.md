# 论文管理

[TOC]
## 修订记录
----

日期 | 作者 | 修订类型 | 修订内容 | 版本
---- | ---- | ---- | ---- | ---- |
2020年04月10日|冷立纲|A|新增设计方案|1.0

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

论文管理相关接口

## 产品说明


## 关键流程说明

## 接口说明


####  列表接口

##### 请求说明

| http 请求方式          | get |
|:------------- |:---------------:|
| url      |/admin/article/list |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| title   | 否 | string  |  标题 |   |
| subjects   | 否 | int  | 学科ID |   |
| field   | 否 | int  | 吸粉领域ID |   |
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
                "id": 7436389,
                "subjects": "12",
                "doi": "https://doi.org/10.1101/2021.03.12.21253495",
                "postDate": 1615564800,
                "pdfUrl": "https://www.medrxiv.org/content/10.1101/2021.03.12.21253495v1.full.pdf",
                "externalId": "/content/10.1101/2021.03.12.21253495v1",
                "isNormal": 1,
                "createTime": 1615889932,
                "updateTime": null,
                "source": "medrxiv",
                "isAuthentication": true,
                "status": true,
                "banReason": null,
                "contactAuthor": null,
                "contactAddress": null,
                "contactEmail": null,
                "scholarId": null,
                "adminId": null,
                "operateIp": null,
                "showId": "cea0cf83408876feb7ef78795e202853",
                "title": "<h1 class=\"highwire-cite-title\" id=\"page-title\">All Models Are Useful: Bayesian Ensembling for Robust High Resolution COVID-19 Forecasting</h1>",
                "authors": "74999533,462839,75474071,75299388,75380655,74742442,74495286,74440341",
                "subjectsNumber": null,
                "keys": null,
                "brief": "<div class=\"section abstract\" id=\"abstract-1\"><p id=\"p-2\">Timely, high-resolution forecasts of infectious disease incidence are useful for policy makers in deciding intervention measures and estimating healthcare resource burden. In this paper, we consider the task of forecasting COVID-19 confirmed cases at the county level for the United States. Although multiple methods have been explored for this task, their performance has varied across space and time due to noisy data and the inherent dynamic nature of the pandemic. We present a forecasting pipeline which incorporates probabilistic forecasts from multiple statistical, machine learning and mechanistic methods through a Bayesian ensembling scheme, and has been operational for nearly 6 months serving local, state and federal policymakers in the United States. While showing that the Bayesian ensemble is at least as good as the individual methods, we also show that each individual method contributes significantly for different spatial regions and time points. We compare our model's performance with other similar models being integrated into CDC-initiated COVID-19 Forecast Hub, and show better performance at longer forecast horizons. Finally, we also describe how such forecasts are used to increase lead time for training mechanistic scenario projections. Our work demonstrates that such a real-time high resolution forecasting pipeline can be developed by integrating multiple methods within a performance-based ensemble to support pandemic response.</p></div>",
                "url": "https://www.medrxiv.org/content/10.1101/2021.03.12.21253495v1"
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}

```



####  详情接口

##### 请求说明

| http 请求方式          | get|
|:------------- |:---------------:|
| url      |/admin/article/read |


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
        "id": 1, //论文ID
        "subjects": "3", //学科，多个用逗号隔开
        "doi": "https://doi.org/10.1101/2020.09.08.287011",  //数字对象唯一标识符
        "postDate": 1599580800, //发表时间
        "pdfUrl": "https://www.biorxiv.org/content/10.1101/2020.09.08.287011v1.full.pdf", //
        "externalId": "10.1101/2020.09.08.287011v1",//原网id
        "isNormal": 1, //状态1为正常，2为异常
        "createTime": 1608889848, //创建时间
        "updateTime": null, //更新时间
        "source": "biorxiv", //来源
        "isAuthentication": true,//是否验证，默认2没验证，1为验证,3为验证失败
        "status": true, //状态，人为正常，2为禁用
        "banReason": null, //禁用理由
        "contactAuthor": null, //联系作者
        "contactAddress": null, //联系地址
        "contactEmail": null, //联系邮箱
        "scholarId": null, //学者ID
        "adminId": null, //管理员ID
        "operateIp": null, //IP
        "showId": "ac73740a2654b8ffc1c090fca04b6d86", //对外ID，title+subjects_number+abstract字段md5，不可改
        "title": "<h1 class=\"highwire-cite-title\" id=\"page-title\">Leaf form diversification in an heirloom tomato results from alterations in two different <em>HOMEOBOX</em> genes</h1>", //文章标题
        "authors": "1,2,3,4,5,6,7",  //作者，多个用逗号隔开
        "subjectsNumber": null,
        "keys": null, //关键词
        "brief": "<div class=\"section abstract\" id=\"abstract-1\"><p id=\"p-4\">Domesticated plants and animals display tremendous diversity in various phenotypic traits and often this diversity is seen within the same species. Tomato (<em>Solanum lycopersicum</em>; Solanaceae) cultivars show wide variation in leaf morphology, but the influence of breeding efforts in sculpting this diversity is not known. Here, we demonstrate that a single nucleotide deletion in the homeobox motif of <em>BIPINNATA</em>, which is a <em>BEL-LIKE HOMEODOMAIN</em> gene, led to a highly complex leaf phenotype in an heirloom tomato, Silvery Fir Tree (SiFT). Additionally, a comparative gene network analysis revealed that reduced expression of the ortholog of <em>WUSCHEL RELATED HOMEOBOX 1</em> is also important for the narrow leaflet phenotype seen in SiFT. Phylogenetic and comparative genome analysis using whole-genome sequencing data suggests that the <em>bip</em> mutation in SiFT is likely a <em>de novo</em> mutation, instead of standing genetic variation. These results provide new insights into natural variation in phenotypic traits introduced into crops during improvement processes after domestication.</p></div>", //简介
        "url": "https://www.biorxiv.org/content/10.1101/2020.09.08.287011v1",
        "visitorCount": 7, //访问人数
        "curiousCount": 4, //好奇人数
        "tags": [
            {
                "type": 2,
                "tagId": 1,
                "value": "测试"
            }
        ],
        "addTime": null
    }
}

```


####  更新接口

##### 请求说明

| http 请求方式          | post json |
|:------------- |:---------------:|
| url      |/admin/article/update |


#####  输入参数

__article参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  ID | |
| subjects   | 否 | int  |  标签类型 |  1 学科标签 2 细分领域标签 3 其他 |
| tags   | 否 | json  |   标签 |  |

__tags参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 是 | int  |  标签类型 |  1 学科 2 细分领域 3 其他    |
| tagId   | 是 | int  |   标签ID |  |
| value   | 是 | string  |   标签值 |  |





##### 请求实例

```json

{
    "id":1,
    "subjects":3,
    "tags":[
        {
            "type":"2",
            "tagId":1,
            "value":"测试"
        }
    ]
}


```


#####  返回实例

```

{
    "id":1,
    "subjects":3,
    "tags":[
        {
            "type":"2",
            "tagId":1,
            "value":"测试"
        }
    ]
}
```


####  添加接口

##### 请求说明

| http 请求方式          | post json |
|:------------- |:---------------:|
| url      |/admin/article/create |


#####  输入参数

__article参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| title   | 是 | string  |   论文标题 |  |
| brief   | 是 | string  |   论文概述 |  |
| uid   | 是 | int  |   用户ID|  |
| subject   | 否 | int  |   学科ID |  |
| field   | 否 | int  |   细分领域ID |  |
| keywords   | 否 | string  |   搜索关键字 |  |
| postDate   | 否 | string  |   发表日期 | yyyy-MM-dd  |
| url   | 是 | string  |   论文地址 |  |
| add_time   | 是 | string  |   添加时间 | yyyy-mm-dd HH:mm:ss  |
| source   | 是 | string  |   期刊|  |
| doi   | 是 | string  |   ；论文标志|  |
| authors   | 是 | string  |   论文作者| 字符串 手写  |
| guideText   | 否 | string  |   text| 导读  |
| guideTitle   | 否 | string  |   text| 导读标题  |
| guideImg   | 否 | string  |   导读图片|  |
| tags   | 否 | json  |   标签 |  |

__tags参数__

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type   | 是 | int  |  标签类型 |  1 学科 2 细分领域 3 其他    |
| tagId   | 是 | int  |   标签ID |  |
| value   | 是 | string  |   标签值 |  |





##### 请求实例

```json

{
    "id":1,
    "subjects":3,
    "tags":[
        {
            "type":"2",
            "tagId":1,
            "value":"测试"
        }
    ]
}


```


#####  返回实例

```

{
    "id":1,
    "subjects":3,
    "tags":[
        {
            "type":"2",
            "tagId":1,
            "value":"测试"
        }
    ]
}
```



####  删除接口

##### 请求说明

| http 请求方式          | post |
|:------------- |:---------------:|
| url      |/admin/article/delete |


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


####  下载用户列表

##### 请求说明

| http 请求方式          | get |
|:------------- |:---------------:|
| url      |/admin/article/download_list |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  ID | |
| page   | 否 | int  |  分页 | 默认值1 |
| limit   | 否 | int  |  每页条数 | 默认值10 |




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
                "id": 234,
                "uid": 10059,
                "mobile": "18813170185",
                "email": "lihang@mittrchina.com",
                "addTime": "2021-04-09 19:46:16"
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}
```


####  浏览用户列表

##### 请求说明

| http 请求方式          | get |
|:------------- |:---------------:|
| url      |/admin/article/visitor_list |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  ID | |
| page   | 否 | int  |  分页 | 默认值1 |
| limit   | 否 | int  |  每页条数 | 默认值10 |




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
                "id": 234,
                "uid": 10059,
                "mobile": "18813170185",
                "email": "lihang@mittrchina.com",
                "addTime": "2021-04-09 19:46:16"
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}
```




