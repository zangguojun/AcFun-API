## 获取手机验证码

#### 调用地址

（**POST**）https://id.app.acfun.cn/rest/web/login/sms/send

#### 参数

| 字段         | 必选   | 类型     | 说明   | 备注                                          |
| ---------- | ---- | ------ | ---- | ------------------------------------------- |
| **mobile** | true | number | 手机号码 |                                             |
| **type**   | true | number | 类型号  | 6：注册新用户(需进行滑块验证)<br />8：绑定新手机号<br />16：找回密码 |

#### 返回

根对象：

| 字段        | 类型     | 说明   | 备注          |
| --------- | ------ | ---- | ----------- |
| result    | number | 结果码  | **详细说明如下表** |
| error_msg | string | 错误信息 | 与result配对   |

###### `result`与`error_msg`对应表：

| result    | error_msg | 备注   |
| --------- | --------- | ---- |
| 0         | 「空」       | 发送成功 |
| 100001013 | 无效手机号     |      |

<details>
<summary>查看示例</summary>

```bash
curl 'https://id.app.acfun.cn/rest/web/login/sms/send' \
    -X POST \
    -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.99 Safari/537.36' \
    -H 'Accept: application/json, text/plain, */*' \
    -H 'Referer: https://www.acfun.cn/' \
    -H 'Content-Type: application/x-www-form-urlencoded' \
    --data-raw 'mobile=手机号码(177xxxx0585)&type=类型号(16)'
```
