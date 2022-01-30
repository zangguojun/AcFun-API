## 获取手机验证码

#### 调用地址

（**POST**）https://id.app.acfun.cn/rest/web/sms/verify

#### 参数

| 字段         | 必选   | 类型     | 说明   | 备注                                    |
| ---------- | ---- | ------ | ---- | ------------------------------------- |
| **mobile** | true | number | 手机号码 |                                       |
| **type**   | true | number | 类型号  | 6：注册新用户<br />8：账号绑定新手机号码<br />16：找回密码 |
| **code**   | true | number | 验证码  | 发送至手机的验证码                             |

#### 返回

根对象：

| 字段        | 字段类型   | 字段说明 | 备注          |
| --------- | ------ | ---- | ----------- |
| result    | int    | 结果码  | **详细说明如下表** |
| error_msg | string | 错误信息 | 与result配对   |

###### `result`与`error_msg`对应表：

| result    | error_msg | 备注   |
| --------- | --------- | ---- |
| 0         | 「空」       | 发送成功 |
| 100001019 | 短信验证码错误   |      |

<details>
<summary>查看示例</summary>

```bash
curl 'https://id.app.acfun.cn/rest/web/sms/verify' \
    -X POST \
    -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.99 Safari/537.36' \
    -H 'Accept: application/json, text/plain, */*' \
    -H 'Referer: https://www.acfun.cn/' \
    -H 'Content-Type: application/x-www-form-urlencoded' \
    --data-raw 'mobile=手机号码(177xxxx0585)&type=类型码(16)&code=验证码(xxxxxx)'
```

<details>
