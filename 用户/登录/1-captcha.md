#### 调用地址

（**GET**）https://id.app.acfun.cn/rest/web/login/captcha

判断指定昵称的用户是否存在

#### 参数：

| 字段     | 必填    | 类型     | 说明  | 备注  |
| ------ | ----- | ------ | --- | --- |
| **__** | fasle | number | 时间戳 | 13位 |

#### 返回值：

##### 根对象：

| 参数名    | 类型     | 内容    | 备注         |
| ------ | ------ | ----- | ---------- |
| result | number | 结果码   | *          |
| image  | str    | 验证码图片 | base64格式图片 |
| key    | number | 图片key |            |

<details>
<summary>查看示例</summary>

```bash
curl -G 'https://id.app.acfun.cn/rest/web/login/captcha'
--data-urlencode '_=时间戳(1643556910454)'
```

<details>