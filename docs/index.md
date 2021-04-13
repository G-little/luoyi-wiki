# 欢迎来络绎直播文档

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## 测试环境说明

* 测试域名 	[http://smileback.xiaogang.org.cn](http://smileback.xiaogang.org.cn)
* 获取上传token接口: {{host}}/upload/token




## 通用接口

### 通用配置接口 

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/config/global |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| platform      | 是| string  |  android/ios |  |



```json

{
c: 0,
m: null,
d: {
    provinces: [
    {
    code: "110000",
    name: "北京"
    }],
    servicePhone: "17301082390"
  }
}

```


### aliyun 上传token接口 

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/upload/token |

#####  输入参数

无



```json

{
    "StatusCode": 200,
    "AccessKeyId": "STS.NUzeDXzATcRoeUddFaeuNZQkR",
    "AccessKeySecret": "DkGbx9v3SrNUjH2G3CDtb1TjCT69J8m7tMThx8YiQrRw",
    "Expiration": "2021-03-28T01:59:04Z",
    "SecurityToken": "CAIS+QF1q6Ft5B2yfSjIr5bPLv7sl5511JCEZ3PVgEY0afpitZTAsDz2IH1EenhsBeoatvU+nmlV6/galqVoRoReREvCKM1565kPCdBwv2WG6aKP9rUhpMCPPwr6UmzavqL7Z+H+U6mqGJOEYEzFkSle2KbzcS7YMXWuLZyOj+wIDLkQRRLqL0AxZrFsKxBltdUROFbIKP+pKWSKuGfLC1dysQcO4gEWq4bHm5LGs0qC0AGjm7JF99ihc6LJNZc8YM1NNP6ux/Fze6b71ypd1gNH7q8ejtYfpGeZ743BWQUJskTcareJrIV1Thd+fq9/EqJBrf7sdHbjdSZ7eO8agAFdejwONHhX+zIInBvx/ZTGFJP5UOvY3PmgG+oU+RE9TIUZ1xkZ91EsdJ9e9vr5ESR56KtJoeQjsxTQ88gJzRkpFWNrE8/I4N4IxEye+CiEJ11va884khDYhp5eiDCPn/5uw0NLunTFuxtshCEri+oG9M7n8cRVUIguR2ozKHrVUQ=="
}

```


#### 1.1 意见反馈

##### 接口说明

意见反馈

##### 请求说明

| http 请求方式          |post             |
|:------------- |:---------------:|
| url      |/feedback/submit |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| feedType      | 否| string    | 举报类型|   |
| content      | 是| string    | 举报内容|   |
| picUrls      | 否| string[]    | 图片|   |
| toUid      | 否| int    | 被举报人|   |


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
