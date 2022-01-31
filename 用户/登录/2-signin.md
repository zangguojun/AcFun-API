## 登录

#### 调用地址

（**POST**）https://id.app.acfun.cn/rest/web/login/signin

判断指定昵称的用户是否存在

#### 参数：

| 字段           | 必填    | 类型  | 说明    | 备注          |
| ------------ | ----- | --- | ----- | ----------- |
| **username** | true  | str | 账号    | 手机号码        |
| **password** | true  | str | 密码    |             |
| **captcha**  | false | str | 图形验证码 | 四个字符(数字/字母) |
| **key**      | false | str | 图片key | captcha返回值  |

#### 返回值：

##### 根对象：

| 字段        | 类型     | 说明     | 备注          |
| --------- | ------ | ------ | ----------- |
| result    | number | 结果码    | **详细说明如下表** |
| error_msg | string | 错误信息   |             |
| userId    | number | 用户ID   |             |
| username  | string | 用户名    |             |
| img       | string | 用户头像链接 | url         |

###### `result`与`error_msg`对应表：

| result    | error_msg  | 含义   |
| --------- | ---------- | ---- |
| 0         | 「空」        | 登录成功 |
| 100001005 | 帐号不存在或密码错误 |      |
| 100001016 | 图片验证码错误    |      |

<details>
<summary>查看示例</summary>

```bash
curl 'https://id.app.acfun.cn/rest/web/login/signin' \
    -X POST \
    -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.99 Safari/537.36' \
    -H 'Accept: application/json, text/plain, */*' \
    -H 'Referer: https://www.acfun.cn/' \
    -H 'Content-Type: application/x-www-form-urlencoded' \
    --data-raw 'username=17719090585&password=5@!46zx-A9c_59Q'
```