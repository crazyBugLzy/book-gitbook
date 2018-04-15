# Gitbook插件

## 功能相关
### 评论 Disqus

[插件地址](https://plugins.gitbook.com/plugin/disqus)
```
"plugins": [
   "disqus"
],
"pluginsConfig": {
   "disqus": {
       "shortName": "gitbookuse"
   }
}
```

> **[warning] For warning**  
> 需要现在disqus网站上注册，然后才能进行评论。在公司内部竟然访问不了 
> disqus网站，所以暂时没有效果。



### 跳转至修改页面 edit-link
```
"plugins": [
    "edit-link"
]
"pluginsConfig": {
    "edit-link": {
        "base": "https://github.com/zhangjikai/gitbook-use/edit/master",
        "label": "Edit This Page"
    }
}
```


### 打赏 donate
```
"plugins": [
    "donate"
]
"pluginsConfig": {
    "donate": {
            "wechat": "https://zhangjikai.com/resource/weixin.png",
            "alipay": "https://zhangjikai.com/resource/alipay.png",
            "title": "",
            "button": "赏",
            "alipayText": "支付宝打赏",
            "wechatText": "微信打赏"
        }
}
```


### 播放本地视频 Local Video

```
"plugins": [ "local-video" ]
```
使用示例：为了使视频可以自适应，我们指定视频的```width```为100%，并设置宽高比为16:9，如下面所示

<!--sec data-id="section1" data-collapse=true data-title="使用示例" data-show=false ces-->

```
{% raw %}
<video id="my-video" class="video-js" controls preload="auto" width="100%"
poster="https://zhangjikai.com/resource/poster.jpg" data-setup='{"aspectRatio":"16:9"}'>
  <source src="https://zhangjikai.com/resource/demo.mp4" type='video/mp4' >
  <p class="vjs-no-js">
    To view this video please enable JavaScript, and consider upgrading to a web browser that
    <a href="http://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a>
  </p>
</video>
{% endraw %}
```
<!--endsec-->

<html>
<button class="section" target="section1" show="使用示例" hide="Hide next section"></button>
</html>


另外我们还要再配置下css，即在website.css中加入

```
.video-js {
    width:100%;
    height: 100%;
}
```

### 搜索插件1：search Pro
支持中文搜索, 需要将默认的search插件去掉, 注意: 如果标题中有包含的关键字, 标题的样式会有所变化
插件地址


```
"plugins": [
    "-search",
    "search-pro"
],
"pluginsConfig": {
    "search-pro": {
        "cutWordLib": "nodejieba",
        "defineWord" : ["Gitbook Use"]
    }
}
```

### 搜索插件2：search-plus
```
"plugins": [
    "-search",
    "search-plus@^0.0.11"
]
```



## 样式相关

介绍顺序按照 网站icon->左侧目录->右侧非内容部分->右侧内容

### 更改网站的 Favicon
[插件地址](https://plugins.gitbook.com/plugin/favicon)

```
{
    "plugins": [
        "favicon"
    ],
    "pluginsConfig": {
        "favicon": {
            "shortcut": "assets/images/favicon.ico",
            "bookmark": "assets/images/favicon.ico",
            "appleTouch": "assets/images/apple-touch-icon.png",
            "appleTouchMore": {
                "120x120": "assets/images/apple-touch-icon-120x120.png",
                "180x180": "assets/images/apple-touch-icon-180x180.png"
            }
        }
    }
}
```

### 左侧宽度可调节 Splitter

```
"plugins": [
    "splitter"
]
```

### 折叠目录 expandable-chapters-small
是左侧的章节目录可以折叠

```
"plugins": ["expandable-chapters-small"]
```

### 目录的层级 theme-default 
修改自带的主题。
```
"pluginsConfig": {
    "theme-default": {
        "showLevel": true
    }
}
```


### 主题选择 prism&prism-themes

主要是嵌入代码块颜色变化。

```
"plugins": [
    "prism@^2.1.0",
    "prism-themes@^0.0.2",
]
"pluginsConfig": {
    "prism": {
        "css": [
            "prism-themes/themes/prism-base16-ateliersulphurpool.light.css"
        ]
    }
}
```


### Toc到侧边悬浮导航&&回到顶部按钮 Anchor-navigation-ex
添加Toc到侧边悬浮导航以及回到顶部按钮。需要注意以下两点：
- 本插件只会提取 h[1-3] 标签作为悬浮导航
- 只有按照以下顺序嵌套才会被提取

[插件地址](https://plugins.gitbook.com/plugin/anchor-navigation-ex)
```
{
    "plugins": [
        "anchor-navigation-ex"
    ],
    "pluginsConfig": {
        "anchor-navigation-ex": {
            "isRewritePageTitle": true,
            "isShowTocTitleIcon": true,
            "tocLevel1Icon": "fa fa-hand-o-right",
            "tocLevel2Icon": "fa fa-hand-o-right",
            "tocLevel3Icon": "fa fa-hand-o-right"
        }
    }
}

```

### 锚点样式 Anchors
[插件地址](https://plugins.gitbook.com/plugin/anchors)

有锚点后就可以跳转到页面的指定位置。

```
"plugins" : [ "anchors" ]
```

### 代码复制按钮 Copy-code-button
[插件地址](https://plugins.gitbook.com/plugin/copy-code-button)

样式不太好看，功能非常实用。

```
{
    "plugins": ["copy-code-button"]
}
```


### Tbfed-pagefooter
为页面添加页脚

```
"plugins": [
   "tbfed-pagefooter"
],
"pluginsConfig": {
    "tbfed-pagefooter": {
        "copyright":"Copyright &copy zhangjikai.com 2015",
        "modify_label": "该文件修订时间：",
        "modify_format": "YYYY-MM-DD HH:mm:ss"
    }
}
```

### 页面分块显示 Sectionx

```
{
    "plugins": [
       "sectionx"
   ],
    "pluginsConfig": {
        "sectionx": {
          "tag": "b"
        }
      }
}
```

使用方式：

<!--sec data-id="section2" data-collapse=true data-title="使用示例" data-show=false ces-->
这就是使用实例了！
<!--endsec-->

<html>
<button class="section" target="section2" show="使用示例" hide="Hide next section"></button>
</html>

### 不同颜色的区块写法 Alerts
添加不同 alerts 样式的 blockquotes，目前包含 info, warning, danger 和 success 四种样式。
下面是使用示例：

<!--sec data-id="section3" data-collapse=true data-title="使用示例" data-show=false ces-->

Info styling
> **[info] For info**
>
> Use this for infomation messages.

Warning styling
> **[warning] For warning**
>
> Use this for warning messages.

Danger styling
> **[danger] For danger**
>
> Use this for danger messages.

Success styling
> **[success] For info**
>
> Use this for success messages.

<!--endsec-->
<html>
<button class="section" target="section3" show="使用示例" hide="Hide next section"></button>
</html>


## 引流相关 (Sharing)

### github
**1. github**  
添加github图标
插件地址

```
"plugins": [ 
    "github" 
],
"pluginsConfig": {
    "github": {
        "url": "https://github.com/zhangjikai"
    }
}
```
**2. github-buttons**

```
"plugins": [ 
    "github-buttons" 
],
"pluginsConfig": {
    "github-buttons": {
            "repo": "zhangjikai/gitbook-use",
            "types": [
                "star"
            ],
            "size": "small"
    }
}
```

### Sharing

```
 plugins: [
 "-sharing"
 "sharing-plus",
 ]
"pluginsConfig": {
    "sharing": {
        "weibo": true,
        "facebook": true,
        "twitter": true,
        "google": false,
        "instapaper": false,
        "vk": false,
        "all": [
            "facebook", "google", "twitter",
                "weibo", "instapaper"
        ]
    }
}
```


## 统计相关
### ga 谷歌统计

```
"plugins": [
    "ga"
 ],
"pluginsConfig": {
    "ga": {
        "token": "UA-XXXX-Y"
    }
}
```

### 百度统计

```
"plugin": [
    "baidu"
 ],
"pluginsConfig": {
    "baidu": {
        "token": "YOUR TOKEN"
    }
}
```






