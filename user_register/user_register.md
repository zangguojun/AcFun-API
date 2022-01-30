# 用户注册相关

## 手机验证码

#### 调用地址

（GET)    https://id.app.acfun.cn/rest/web/login/sms/send

#### 参数

| 字段   | 必选  | 类型 | 说明     | 备注                                                       |
| ------ | ----- | ---- | -------- | ---------------------------------------------------------- |
| mobile | true  | int  | 手机号码 |                                                            |
| type   | true  | int  | 类型号   | 6：注册新用户<br />8：账号绑定新手机号码<br />16：找回密码 |
|        | false |      | 空段     |                                                            |

如  https://id.app.acfun.cn/rest/web/login/sms/send?mobile=17194242614&type=6&

#### 返回

##### 返回标准Json格式（参考文件请见同级目录下send_*.json文件)

##### Json格式下字段如下

| 字段      | 字段类型 | 字段说明 | 备注                                                    |
| --------- | -------- | -------- | ------------------------------------------------------- |
| result    | int      | 结果码   | 0：发送成功（error_msg为空）<br />100001013：无效手机号 |
| error_msg | string   | 错误信息 | 与result配对                                            |



## 用户注册

#### 调用地址

（POST)   https://id.app.acfun.cn/rest/web/register/mobileCode 

#### 参数

| 字段      | 必选 | 类型   | 说明       |
| --------- | ---- | ------ | ---------- |
| username  | true | string | 可用用户名 |
| mobile    | true | int    | 手机号码   |
| code      | true | int    | 手机验证码 |
| password  | true | int    | 密码设置   |
| password2 | true | int    | 重复密码   |

如   https://id.app.acfun.cn/rest/web/register/mobileCode?username=zangguojun&mobile=17194242614&code=222954&password=5@!46zx-A9c_59Q&password2=5@!46zx-A9c_59Q

#### 返回

##### 返回标准Json格式（参考文件请见同级目录下register_*.json文件)

##### Json格式下字段如下

| 字段      | 字段类型 | 字段说明   | 备注                                                       |
| --------- | -------- | ---------- | ---------------------------------------------------------- |
| error_msg | string   | 错误信息   | 与result配对                                               |
| result    | int      | 检验结果码 | 100001019：验证码错误<br />100001007：手机号已被注册或绑定 |







