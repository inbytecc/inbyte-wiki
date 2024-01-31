# Content 内容区域规范

# **目的**

为适配详情介绍内容在小程序、App 的通用性，并且在图文视频混合情况下，能更好控制对象存储空间，设定以下规范



# **文本字段命名**

统一使用 content，或 xxxContent，表示这是一个富文本，混合图文视频详情展示区



# **字段结构**

数组结构，每个对象包含字段【dataType, value, action, path, param】

id: 数据对象ID



#### **dataType：数据类型**

| 值   | 字典名               | 作用       | 说明                                              |
| ---- | -------------------- | ---------- | ------------------------------------------------- |
| 0    | text                 | 普通文本   | 字号14，字体边距等样式内容待补充                  |
| 1    | richText             | 富文本     | 包含常用html，emoji表情，等配置但不包含视频和图片 |
| 2    | image                | 图片       | 默认不能点击打开，以及保存                        |
| 3    | video                | 视频       | 在 WiFi 环境下默认自动播放，否则显示播放按钮      |
| 4    | channelVideoEmbed    | 内嵌视频号 | 默认开启自动，循环播放；不静音                    |
| 5    | channelVideoRedirect | 跳转视频号 | 同上样式类似下一行[点击查看视频](https://x.x.x)   |



#### **视频号数据**

当 dataType 为 4 或 5 时，内嵌视频，与跳转视频

| 字段                  | 说明        |      |
| --------------------- | ----------- | ---- |
| feedId                | 视频 feedId |      |
| channelVideoAccountId | 视频号 id   |      |
|                       |             |      |





#### **value：数据值**

| 字典     | 值类型          |
| -------- | --------------- |
| text     | 文本内容        |
| richText | html 富文本内容 |
| image    | 图片 URL 地址   |
| video    | 视频 URL 地址   |



#### **action：行为**

| 字典 | 事件处理   |      |
| ---- | ---------- | ---- |
| 0    | 无         |      |
| 1    | 小程序跳转 |      |
| 2    | 浏览器跳转 |      |



#### **path：路径**

当 action 为1, 2时，对应的跳转路径



#### **param：参数**

跳转参数，类似地址问号后待的参数

参数直接【&】and符号连接



#### **数据示例：**

[

{"dataType":0, "value":"文字介绍信息"},

{"dataType":1, "value":"<a>html标签内容</a>"},

{"dataType":1, "value":"<a>点击此处跳转课程详情</a>", "path":"course/index", "pathParam":"courseId=1"},

{"dataType":2, "value":"https://prod-resource-pub.xiaomai5.com/inst/1573240027134676994/website/20221020095323/K88bw7yhnynb5XjY.jpeg"},

{"dataType":2, "value":"https://cdn.inbyte.com/image/sample", "action": 1, "path": "page/home/index", "param":"homeId=1&shareUserId=2"},

{"dataType":3, "value":"[https://www.eaststarcamp.com/Public/image/xcsp.mp4"}](https://www.eaststarcamp.com/Public/image/xcsp.mp4)

]



#### **品牌介绍**

[

{"dataType":3, "value":"https://www.eaststarcamp.com/Public/image/xcsp.mp4"},

{"dataType":2, "value":"https://prod-resource-pub.xiaomai5.com/inst/1573240027134676994/website/20221020095323/K88bw7yhnynb5XjY.jpeg"},

{"dataType":2, "value":"https://prod-resource-pub.xiaomai5.com/inst/1573240027134676994/website/20221020100058/2MbntEfDXJHNQWQp.jpeg"},

{"dataType":2, "value":"https://prod-resource-pub.xiaomai5.com/inst/1573240027134676994/website/20221020095337/mAcdK6ppTtrenwnM.jpeg"},

{"dataType":2, "value":"https://prod-resource-pub.xiaomai5.com/inst/1573240027134676994/website/20221020095346/sXENKexrzxZJ7RCn.jpeg"},

{"dataType":2, "value":"https://prod-resource-pub.xiaomai5.com/inst/1573240027134676994/website/20221020095357/xK2y732W5DHZn6Fm.jpeg"},

{"dataType":2, "value":"https://prod-resource-pub.xiaomai5.com/inst/1573240027134676994/website/20221020095404/S5ZmeDNsBEAAYzFy.jpeg"},

{"dataType":2, "value":"https://prod-resource-pub.xiaomai5.com/inst/1573240027134676994/website/20221020095412/mkxFZtkH3k7sMjwT.jpeg"},

{"dataType":2, "value":"https://prod-resource-pub.xiaomai5.com/inst/1573240027134676994/website/20221020095424/MQXbnj7JtWGWMC22.jpeg"},

]

|      |      |      |      |
| ---- | ---- | ---- | ---- |
|      |      |      |      |
|      |      |      |      |
|      |      |      |      |
|      |      |      |      |
|      |      |      |      |
|      |      |      |      |