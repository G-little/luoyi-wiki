


#### 1.1 论文详情

##### 接口说明

创建会议

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/article/detail |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是 | int  |  论文ID |    |


#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "id": 1,
        "title": "Leaf form diversification in an heirloom tomato results from alterations in two different HOMEOBOX genes",
        "authors": [ //作者
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
        "curiousCount": 0,
        "brief": "Domesticated plants and animals display tremendous diversity in various phenotypic traits and often this diversity is seen within the same species. Tomato (Solanum lycopersicum; Solanaceae) cultivars show wide variation in leaf morphology, but the influence of breeding efforts in sculpting this diversity is not known. Here, we demonstrate that a single nucleotide deletion in the homeobox motif of BIPINNATA, which is a BEL-LIKE HOMEODOMAIN gene, led to a highly complex leaf phenotype in an heirloom tomato, Silvery Fir Tree (SiFT). Additionally, a comparative gene network analysis revealed that reduced expression of the ortholog of WUSCHEL RELATED HOMEOBOX 1 is also important for the narrow leaflet phenotype seen in SiFT. Phylogenetic and comparative genome analysis using whole-genome sequencing data suggests that the bip mutation in SiFT is likely a de novo mutation, instead of standing genetic variation. These results provide new insights into natural variation in phenotypic traits introduced into crops during improvement processes after domestication."
    }
}

```




#### 1.2 论文列表

##### 接口说明

创建会议

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/article/list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| parentSubjectType      | 否 |  int  |  学科领域 |    |
| subjectTypes      | 否 |  int[]  |  细分领域数组 |    |
| page      | 否 |  int  |  分页 |    |
| limit      | 否 |  int  |  限制条数 |    |

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
                "visitorBrief": [
                    {
                        "nickname": null,
                        "avatar": null,
                        "uid": 10002,
                        "jobTitle": null
                    }
                ],
                "visitorCount": 1,
                "curiousCount": 0,
                "curious": true
            }
        ],
        "end": false,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}

```




#### 1.3 好奇论文

##### 接口说明

创建会议

##### 请求说明

| http 请求方式          |put             |
|:------------- |:---------------:|
| url      |/article/curious |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是 |  int  |  文章ID |    |
| value      | 否 |  boolean  |  true/false |     |

#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
    }
}

```


#### 1.4 下载论文

##### 接口说明

创建会议

##### 请求说明

| http 请求方式          |put             |
|:------------- |:---------------:|
| url      |/article/download |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是 |  int  |  文章ID |    |

#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
    }
}

```











