# Github Search API文档

## 概览

1. 查询搜索热词
2. 搜索开源项目

## 1. 查询搜索热词

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| GET | https://gitstars.cn/search/hotwords.json |

* 返回结果

    + AJAX请求成功

        ```
        [
          "Swift",
          "awesome",
          "React"
        ]
        ```

## 2. 搜索开源项目

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| GET | /search.json |

* 参数描述

| 参数关键字 | 是否可选 | 格式 | 描述 |
| :-- | :-- | :-- | :-- |
| q | 必传 | 字符串 | 搜索关键字 |
| page | 可选 | 从1开始的数字 | 页码，不传，默认为1 |
| per_page | 可选 | 0以上的数字 | 每页数据条数, 不传，默认为20 |
| sort | 可选 | 枚举常量见下部 | 见下部 |
| order | 可选 | asc或者desc | 正序或者逆序，默认为desc（逆序） |

* sort 参数描述

    + `in` Qualifies which fields are searched. With this qualifier you can restrict the search to just the repository name, description, readme, or any combination of these.
    + `size` Finds repositories that match a certain size (in kilobytes).
    + `forks` 按照 Forks 的数量过滤
    + `fork` Filters whether forked repositories should be included (true) or only forked repositories should be returned (only).
    + `created` or `pushed` Filters repositories based on date of creation, or when they were last updated.
    + `user` or `repo` Limits searches to a specific user or repository.
    + `language` 按照语言过滤
    + `stars` 按照 Stars 的数量过滤

* 返回结果

    + 返回数据类型

    ```json
    [
      {
        "name": "qs-lll/ExpandingPager",
        "desc": "ExpandingPager is a card peek/pop controller",
        "stars_count": 647,
        "language": "Java",
        "readme": "https://api.github.com/repos/qs-lll/ExpandingPager/readme"
      }
    ]
    ```

    + 如果是第一页，会包含以下数据，建议的语言过滤项和其他搜索的数量提示

    ```
    ...
    language_filter: {
        Ruby: "16",
        Shell: "10",
        JavaScript: "2",
        Perl: "1"
    },
    type_counter: {
        repos_count: 36,
        code_count: "17,734",
        issues_count: "4,688",
        users_count: "1"
    }
    ...
    ```


