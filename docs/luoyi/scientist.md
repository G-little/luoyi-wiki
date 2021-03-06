


#### 1.1 提交认证

##### 接口说明

提交科学家认证信息

##### 请求说明

| http 请求方式          |post             |
|:------------- |:---------------:|
| url      |/scientist/cert/commit |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| imageUrl      | 是 | string  |  认证信息 |    |


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




#### 1.2 获取认证信息

##### 接口说明

获取认证信息

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/scientist/cert/get |

#####  输入参数


#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "uid":1111,
        "certStatus":0, //认证状态 0 初始 1 待审核 2 通过 -1 驳回
        "imageUrl":"/xxxx" //认证图
   }
}

```




#### 1.3 取消认证

##### 接口说明

取消认证

##### 请求说明

| http 请求方式          |put             |
|:------------- |:---------------:|
| url      |/scientist/cert/cancel |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| reason      | 是 |  string  |   取消原因 |    |

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


#### 1.4 banner 列表

##### 接口说明

广告认证

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/banner/list |

#####  输入参数

无

#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": [{
        "id":1, //广告ID
        "title":"标题", //标题
        "type": 1, //广告类型 
        "imageUrl": "/xxx", //广告图片 
        "linkId": 1 //关联ID
    }]
}

```



#### 1.5 科学家推荐

##### 接口说明

科学家推荐

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/scientist/list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| page      | 否 |  int  |   分页 |    |
| limit      | 否 |  int  |   分页条数 |    |


#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "total": 2147483647,
        "currentPage": 1,
        "list": [
            {
                "feed": { //跟动态表保持一致
                    "id": 122,
                    "uid": 10175,
                    "addTime": 1619397599214,
                    "type": 2,
                    "targetId": 100066,
                    "ext": {
                        "type": 1,
                        "meetingId": 100066,
                        "coverUrl": "",
                        "title": "学术直播",
                        "playUrl": "http://1305362003.vod2.myqcloud.com/0beee439vodcq1305362003/5bb91ab75285890817467138691/playlist.m3u8",
                        "userBrief": [
                            {
                                "uid": 10175,
                                "avatar": "0136fd66bf9ba616d354a6f15b0a18ce.png",
                                "name": "冷小纲",
                                "workplace": "都柏林大学",
                                "jobTitle": null,
                                "meetingRole": 1
                            }
                        ]
                    },
                    "followStatus": null
                },
                "user": {  //用户信息
                    "uid": 10175, //用户ID
                    "avatar": "0136fd66bf9ba616d354a6f15b0a18ce.png", //头像
                    "name": "冷小纲", //昵称
                    "workplace": "都柏林大学", //学校
                    "jobTitle": null, //头衔
                    "followStatus": 0 //关注状态
                }
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0,
        "totalPage": -214748364
    }
}

```




#### 1.6 专辑列表

##### 接口说明

科学家推荐

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/album/list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| page      | 否 |  int  |   分页 |    |
| limit      | 否 |  int  |   分页条数 |    |


#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "total": 2147483647,
        "currentPage": 1,
        "list": [
            {
                "id": 1, //专辑ID
                "title": "test", //标题
                "brief": "test", //简述
                "imageUrl": "/test", //图片
                "sortField": null, //排序字段
                "userCount": 1, //用户数
                "addTime": null //添加时间
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0,
        "totalPage": -214748364
    }
}
```


#### 1.7 专辑科学家列表

##### 接口说明

科学家推荐

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/album/item_list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| page      | 否 |  int  |   分页 |    |
| limit      | 否 |  int  |   分页条数 |    |
| id      | 是 |  int  |   专辑ID |    |


#####  错误说明





#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "total": 2147483647,
        "currentPage": 1,
        "list": [
            {
                "uid": 10175, //用户ID
                "avatar": "0136fd66bf9ba616d354a6f15b0a18ce.png",//头像
                "name": "冷小纲", //昵称
                "workplace": "都柏林大学",//大学
                "jobTitle": null, //头衔
                "followStatus": 0, //关注状态
                "brief": null //简述
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0,
        "totalPage": -214748364
    }
}
```












