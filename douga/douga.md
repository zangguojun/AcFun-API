## 分页读取TV动画列表

#### 调用地址

（GET) https://www.acfun.cn/v/list67/index.htm

| 字段          | 必选    | 类型     | 说明     | 备注                                                                                                                                                                                                                                                                              |
| ----------- | ----- | ------ | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sortField   | false | string | 排序方式   | `rankScore`：综合（默认）<br />`createTime`：最新投稿<br />`viewCount`：播放最多<br />`commentCount`：评论最多<br />`danmakuCount`：弹幕最多<br />不加参，默认为`rankScore`                                                                                                                                       |
| duration    | false | string | 时长     | `all`：全部（默认）<br />`0,5`：5分钟以下<br />`5,30`：5-30分钟<br />`30,60`：30-60分钟<br />`60,`：60分钟以上<br />不加参，默认为`all`                                                                                                                                                                       |
| date        | false | string | 年份     | `default`：近三个月<br />`20200101,20210101`：2020<br />`20190101,20200101`：2019<br />`20180101,20190101`：2018<br />`20170101,20180101`：2017<br />`20160101,20170101`：2016<br />`20150101,20160101`：2015<br />`20100101,20150101`：2010-2014<br />`,20100101`：更早<br />不加参，默认为`default` |
| page        | true  | int    | 页数     | 不加参，默认`page=1`                                                                                                                                                                                                                                                                  |
| quickViewId | true  | string | 板块名    | `ac-space-video-list`：视频板块<br />`bangumiList`：番剧板块<br />`listwrapper`：TV动画                                                                                                                                                                                                      |
| reqID       | false | int    | 请求次数   |                                                                                                                                                                                                                                                                                 |
| ajaxpipe    | true  | int    | 返回数据类型 | `1`：类似Json类型                                                                                                                                                                                                                                                                    |
| t           | false | int    | 13位时间戳 |                                                                                                                                                                                                                                                                                 |

| 字段          | 必选    | 类型     | 说明    | 备注              |
| ----------- | ----- | ------ | ----- | --------------- |
| `续上表`       | `续上表` | `续上表`  | `续上表` | `续上表`           |
| `sortField` | false | string | 同上    | 重复上表`sortField` |
| `duration`  | false | string | 同上    | 重复上表`duration`  |
| `date`      | false | string | 同上    | 重复上表`date`      |

如 https://www.acfun.cn/v/list67/index.htm?sortField=rankScore&duration=all&date=default&page=2&quickViewId=listwrapper&reqID=1&ajaxpipe=1&sortField=rankScore&duration=all&date=default&page=2&t=1596895987003 

官方需要传递两次`sortField`、`date`和`duration`参数，请求一次也是完全OK的。

#### 返回

##### 返回文本文件，形如 （参考文件请见同级目录下TV_douga.txt文件)

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

###### html字段 (参考文件请见同级目录下TV_douga.html文件)

## 分页读取剧场动画列表

#### 调用地址

（GET) https://www.acfun.cn/v/list180/index.htm

## 分页读取国产动画列表

#### 调用地址

（GET) https://www.acfun.cn/v/list120/index.htm

### `剧场动画`与`国产动画`的参数`TV动画`的参数一模一样,可参照TV动画

> ### 截止到现在，**番剧板块**中`番剧列表`，`TV动画`，`剧场动画`以及`国产动画`的 API 已经全部收集完毕。如同级目录`fanju.png`
