#### 调用地址

（**POST**）https://www.acfun.cn/rest/pc-direct/user/checkNameUnique

判断指定昵称的用户是否存在

#### 参数：

| 字段       | 必填   | 类型  | 说明   | 备注                       |
| -------- | ---- | --- | ---- | ------------------------ |
| **name** | true | str | 目标昵称 | 昵称长度在2-16字之间，且不包含空格或特殊符号 |

#### 返回值：

##### 根对象：

| 参数名       | 类型     | 内容     | 备注          |
| --------- | ------ | ------ | ----------- |
| result    | number | 结果码    | **详细说明如下表** |
| error_msg | str    | 错误信息   |             |
| host-name | str    | 检验机主机名 |             |

###### `result`与`error_msg`对应表：

| result | error_msg                  | 含义        |
| ------ | -------------------------- | --------- |
| 0      | 「空」                        | 昵称未被注册    |
| 108002 | 昵称已被占用                     | 该昵称已被他人使用 |
| 108122 | 昵称长度应在2~16位，并且不能包含符号以及特殊字符 | 昵称不满足上述规范 |

<details>
<summary>查看示例</summary>

```bash
curl 'https://www.acfun.cn/rest/pc-direct/user/checkNameUnique' \
    -X POST \
    -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.99 Safari/537.36' \
    -H 'Accept: application/json, text/plain, */*' \
    -H 'Referer: https://www.acfun.cn/' \
    -H 'Content-Type: application/x-www-form-urlencoded' \
    --data-raw 'name=用户名(zangguojun)'
```

<details>
