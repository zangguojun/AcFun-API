## 分页读取番剧列表

#### 调用地址

（GET)  https://www.acfun.cn/bangumilist

#### 参数

| 字段        | 必选  | 类型   | 说明         | 备注                                                         |
| ----------- | ----- | ------ | ------------ | ------------------------------------------------------------ |
| filters     | false | string | 过滤方式     | 详情见同级目录下`filters.md`文件                             |
| pageNum     | true  | int    | 页数         | 不加参，默认`page=1`                                         |
| quickViewId | true  | string | 板块名       | `ac-space-video-list`：视频板块<br />`bangumiList`：番剧板块<br />`listwrapper`：TV动画 |
| reqID       | false | int    | 请求次数     |                                                              |
| ajaxpipe    | true  | int    | 返回数据类型 | `1`：类似Json类型                                            |
| t           | false | int    | 13位时间戳   |                                                              |
| `filters`   | false | string | 同上         |                                                              |
| `pageNum`   | false | int    | 同上         |                                                              |

如  https://www.acfun.cn/bangumilist?filters=10,20,30,40,50,805306368&pageNum=4&quickViewId=bangumiList&reqID=5&ajaxpipe=1&filters=10,20,30,40,50,805306368&pageNum=4&t=1596688476553 

> 不清楚官方为什么需要传递两次`filters`和`pageNum`参数，请求一次也是完全OK的。话说官方在请求数据的时候也发送了两个一模一样的请求，咱们不知道，咱们也不敢问。

#### 返回

##### 返回文本文件，形如 （参考文件请见同级目录下bangumilist.txt文件)

```
Json格式文本 + /*<!-- fetch-stream -->*/
```

##### Json格式下字段如下

| 字段   | 字段类型 | 字段说明           |
| ------ | -------- | ------------------ |
| html   | HTML     | 返回作品详细信息   |
| js     | string   | 引入的JS文件链接   |
| css    | string   | 引入的CSS文件链接  |
| styles | string   | 引入的样式文件链接 |
| script | string   | 引入的脚本文件链接 |

###### html字段 (参考文件见同级目录下bangumilist.html文件以及bangumilist.png结构图)









