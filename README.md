# :gift:Present-FEE

Present is **presented** by Zapic:gift_heart:.  
Present is **Fixed** and **Enhanced** by ***[taosuayou](https://github.com/taosuayou/Present-FE)***

一个简洁的个人主页,支持显示博客文章/随机背景图片/随机语句.  

![preview.gif](https://raw.gitmirror.com/taosuayou/Present-FE/refs/heads/main/preview.png)


## 4.12, 2025 
- [x] 更改为本地音乐播放，可以删除meting注释来调用网络音乐
- [x] 新增运行时间，可在index.html中调整
- [x] 根据时间确定工作和休息时间
- [x] 修复部分样式问题

## 🎉 修复和增强

- [x] 修复并升级Fontawesome至6.x
- [x] 优化配色
- [X] 增加音乐播放器
- [x] 解决移动端底部版权信息重叠问题
- [x] 更快的js cdn
- [x] 背景图为bing每日壁纸
- [x] more...

### Browser support:
|  IE   | Chrome  | Firefox   | Other  |
|  ----  | ----  |  ----  | ----  |
| 11+(Partial Support)  | 49+ | 52+  | (?) |

## USAGE

> [!NOTE]
>
> 1. 如果使用cloudflare cdn请不要开启[Rocket Loader™](https://dash.cloudflare.com/speed/optimization/content)或[单独配置规则](https://dash.cloudflare.com/rules/configuration-rules)，否则会卡在Loading页面
> 2. 不要删除版权©信息谢谢

### 随机背景图片
> [!IMPORTANT]
>
> 默认使用的是[`bing壁纸api`](https://github.com/mcxiaolan/bing-image-api)

1. 将图片放入`static/img/`内.
2. 建议放入一个图片的缩略图优化加载体验.
3. 在`index.html`内找到`var bgArr = [...`
4. 按以下格式添加一个对象:
```
{
	"url": "url/path",
	"thumb": "url/path" // 如果没有缩略图,可以留空.
}
```
5. 如果不会可以简单的学一下`JavaScript`语法.

### 播放器设置
1. 在`index.html`内`101`行
2. 参考`aplayer`和`meting`官方文档
3. 必要参数解释:
|  option   | default  | description   |
|  ----  | ----  |  ----  |
| id  | require | song id / playlist id / album id / search keyword  |
|  ----  | ----  |  ----  |
| server  | require | music platform:`netease`, `tencent`, `kugou`, `xiami`, `baidu`  |
|  ----  | ----  |  ----  |
| type  | require | `song`, `playlist`, `album`, `search`, `artist`  |

### 随机语句
1. 在`index.html`内找到`var senArr = [...`
2. 按照[Typinyin.js](https://github.com/ClassicOldSong/typinyin.js)的文档添加语句.
3. 如果不会可以简单的学一下`JavaScript`语法.


### 博客文章输出

#### XML模式(默认配置)
此模式**需设置** 跨域,无需提供PHP支持,由前端解析XML文档,传输数据量较多,在无PHP环境情况下推荐使用.  
此处不提供跨域教程,请自行搜索.

1. 在`index.html`内找到`var feedType=...`,修改为`xml`,
2. 在`index.html`内找到`var feedPath=...`,修改为你的博客RSS地址,如`https://blog.me/atom.xml`;
3. 如果不会可以简单的学一下`JavaScript`语法.

#### JSON模式
此模式无需设置跨域,仅需提供PHP支持,由后端解析XML文档,传输数据量较少,推荐使用.  
**注意:** 使用本功能,你的服务器必须支持`PHP 5.6+`,并启用`XML`拓展.

1. 在`index.html`内找到`var feedType=...`,修改为`json`.
2. 在`feed.php`内找到`$feed_url`;
3. 将`$feed_url`修改为你的博客RSS订阅地址.
4. 如果不会可以简单的学一下`PHP`语法.

### 链接图标
链接图标列表: [Font Awesome](https://fontawesome.com/)
<details>
<summary>tip</b></summary><br>

进不去请挂梯子或者bing找中国镜像

</details>

1. 在列表里找到心仪的图标
2. 点击`复制`按钮
3. 找到需要修改的图标(图标元素均为`i`,拥有`fa`类)
4. 删除原有的图标class(`fa-*`),将新的粘贴进去.