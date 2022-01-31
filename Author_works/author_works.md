## 分页读取作者作品

#### 调用地址

（GET) https://www.acfun.cn/u/ + authorID 

#### 参数

| 字段          | 必选    | 类型     | 说明     | 备注                                       |
| ----------- | ----- | ------ | ------ | ---------------------------------------- |
| quickViewId | true  | string | 板块名    | ac-space-video-list：视频板块bangumiList：番剧板块 |
| reqID       | false | int    | 请求次数   |                                          |
| ajaxpipe    | true  | int    | 返回数据类型 | 1：类似Json类型                               |
| type        | true  | string | 作品类型   | video：视频                                 |
| order       | false | string | 排序方式   | newest：最新排序<br />hotest：最火排序             |
| page        | true  | int    | 页数     | 不加参，默认为第一页                               |
| pageSize    | true  | int    | 单页作品数  |                                          |
| t           | false | int    | 13位时间戳 |                                          |

如 https://www.acfun.cn/u/4471111?quickViewId=ac-space-video-list&reqID=1&ajaxpipe=1&type=video&order=newest&page=1&pageSize=20&t=1596683321689 

#### 返回

##### 返回文本文件，形如 （参考文件请见同级目录下author_works.txt文件)

```
Json格式文本 + /*<!-- fetch-stream -->*/
```

##### Json格式下字段如下

| 字段     | 字段类型   | 字段说明       |
| ------ | ------ | ---------- |
| html   | HTML   | 返回作品详细信息   |
| js     | string | 引入的JS文件链接  |
| css    | string | 引入的CSS文件链接 |
| styles | string | 引入的样式文件链接  |
| script | string | 引入的脚本文件链接  |

###### html字段 (参考文件请见同级目录下author_works.html文件以及author_works.png结构图)
