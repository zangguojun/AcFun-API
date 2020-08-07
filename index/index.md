

## AcFun首页

#### 调用地址

（GET)  https://www.acfun.cn/

#### 参数

| 字段     | 必选  | 类型   | 说明         | 备注            |
| -------- | ----- | ------ | ------------ | --------------- |
| pagelets | true  | string | 板块名       | **详见下表**    |
| reqID    | false | int    | 请求次数     |                 |
| ajaxpipe | true  | int    | 返回数据类型 | 1：类似Json类型 |
| t        | false | int    | 13位时间戳   |                 |

##### pagelets 参数表

| 字段             | 说明      | 内容                                                         |
| ---------------- | --------- | ------------------------------------------------------------ |
| pagelet_life     | 生活      | 推荐视频（10个视频）<br />排名榜（包括日榜，三日榜，周榜）（每榜5个视频）<br />【详情请看`pagelet_life`文件夹】 |
| pagelet_fishpond | 鱼塘      | 同`pagelet_life`<br />【详情请看`pagelet_fishpond`文件夹】   |
| pagelet_sport    | 体育      | 同`pagelet_life`<br />【详情请看`pagelet_sport`文件夹】      |
| pagelet_music    | 音乐      | 同`pagelet_life`<br />【详情请看`pagelet_music`文件夹】      |
| pagelet_tech     | 科技      | 同`pagelet_life`<br />【详情请看`pagelet_tech`文件夹】       |
| pagelet_dance    | 舞蹈·偶像 | 同`pagelet_life`<br />【详情请看`pagelet_dance`文件夹】      |
| pagelet_film     | 影视      | 同`pagelet_life`<br />【详情请看`pagelet_film`文件夹】       |
| pagelet_douga    | 动画      | 推荐视频（1大封面+11小封面动画）<br />排名榜（包括日榜，三日榜，周榜）（每榜10个视频）<br />【详情请看`pagelet_douga`文件夹】 |
| pagelet_game     | 游戏      | 同`pagelet_douga`<br />【详情请看`pagelet_game`文件夹】      |
| 字段                 | 说明     | 内容                                                         |
| -------------------- | -------- | ------------------------------------------------------------ |
| `续上表`             | `续上表` | `续上表`                                                     |
| pagelet_bangumi_list | 番剧     | 放映时间表（包括周一到周日）（每天最多7个番）<br />新番发布（10个番）<br />本季安利（3个番）<br />【详情请看`pagelet_bangumi_list`文件夹】 |

如 https://www.acfun.cn/?pagelets=pagelet_game,pagelet_douga,pagelet_bangumi_list,pagelet_life,pagelet_tech,pagelet_dance,pagelet_music,pagelet_film,pagelet_fishpond,pagelet_sport&reqID=0&ajaxpipe=1&t=1596778906245

#### 返回

##### 返回文本文件，形如 （参考文件请见同级目录下index.txt文件`参考中请求了多个板块`)

```
Json格式文本 + /*<!-- fetch-stream -->*/ + Json格式文本 + /*<!-- fetch-stream -->*/ +
Json格式文本 + /*<!-- fetch-stream -->*/ + Json格式文本 + /*<!-- fetch-stream -->*/ ....
即以 `Json格式文本 + /*<!-- fetch-stream -->*/` 为单元的文本文件，每个Json格式文本字段相同，单元数与请求字段`pagelets`的个数相同，若`pagelets`只请求一个版块，则只返回一个单元
```

##### Json格式文本字段如下

| 字段      | 字段类型 | 字段说明           | 内容                                                       |
| --------- | -------- | ------------------ | ---------------------------------------------------------- |
| container | string   |                    |                                                            |
| id        | string   | 请求板块名         | 请求字段`pagelets`的组成单元                               |
| html      | HTML     | 返回作品详细信息   | 对应板块HTML代码<br />【详情请看对应文件夹下`*.html`文件】 |
| js        | string   | 引入的JS文件链接   |                                                            |
| css       | string   | 引入的CSS文件链接  |                                                            |
| styles    | string   | 引入的样式文件链接 |                                                            |
| script    | string   | 引入的脚本文件链接 |                                                            |
| mode      | sting    |                    | normal：正常                                               |

### 剩余板块（漏网之鱼）

> 其实在ACFun首页中，仍有娱乐板块、香蕉榜板块、猴子推荐板块、轮播图和总推荐视频板块，没能从上述地址请求数据。







