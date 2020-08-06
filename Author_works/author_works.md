## 分页读取作者作品

#### 调用地址

（GET) https://www.acfun.cn/u/ + authorID 

#### 参数

| 字段        | 必选  | 类型   | 说明       |
| ----------- | ----- | ------ | ---------- |
| quickViewId | true  | string | 显示格式   |
| reqID       | false | int    | 请求次数   |
| ajaxpipe    | true  | int    | 固定值     |
| type        | true  | string | 作品类型   |
| order       | true  | string | 排序方式   |
| page        | true  | int    | 页数       |
| pageSize    | true  | int    | 单页作品数 |
| t           | false | int    | 13位时间戳 |

如 https://www.acfun.cn/u/4471111?quickViewId=ac-space-video-list&reqID=1&ajaxpipe=1&type=video&order=newest&page=1&pageSize=20&t=1596683321689 

#### 返回

##### 返回文本文件，形如 （参考文件请见同级目录下test.txt文件)

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

###### html字段 (参考文件请见同级目录下test.html文件以及test.png结构图)









