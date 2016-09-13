# Github Explore API文档

## Github 趋势项目

> 同步于 Github Trending，目前更新的频率为2小时，会缓存 readme 数据到大陆 CDN。

### 获取 Trending 编程语言列表

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| GET | https://gitstars.cn/trending/languages.json |

* 返回结果

    + AJAX请求成功

        ```
        [
          "unknown",
          "ruby",
          "java",
          "javascript",
          "c",
          "cpp",
          "objective-c",
          "swift",
          "python",
          "php"
        ]
        ```

### 获取 Trending 项目列表

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| GET | https://gitstars.cn/trending.json |

* 参数描述

| 参数关键字 | 格式 | 描述 |
| :-- | :-- | :-- |
| lang | 不传此参数默认为all，可以传入all或者 `获取 Trending 编程语言列表` 接口所返回数据包含的值 | 编程语言 |

* 返回结果

    + AJAX请求成功

        ```
        [
          {
            name: "infinitered/ignite",
            desc: "The ideal starting app for React Native",
            stars_count: 213,
            stars_increasing: 0,
            language: "JavaScript",
            icon: "https://avatars.githubusercontent.com/u/3902527?v=3",
            readme: "https://o7br2e26q.qnssl.com/readme/infinitered/ignite-1464958823.json"
          },
          {
            name: "Dimezis/BlurView",
            desc: "hidden",
            stars_count: 34,
            stars_increasing: 0,
            language: "Java",
            icon: "https://avatars.githubusercontent.com/u/1433500?v=3",
            readme: "https://o7br2e26q.qnssl.com/readme/Dimezis/BlurView-1465034422.json"
          },
          ... /*省略*/
        ]
        ```
