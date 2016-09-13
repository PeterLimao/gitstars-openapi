## 个人stars项目列表

### 1. 开始从github同步stars

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| POST | https://gitstars.cn/stars/sync.json |

### 2. 获取从github同步stars的状态

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| GET | https://gitstars.cn/stars/sync.json |

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| PUT | https://gitstars.cn/github/{:user}/{:name}.json |

### 3. stars 数据 （GET 请求）
   [https://gitstars.cn/stars.json](http://test01.gitstars.cn/stars.json)
   
   + 获取个人stars数据列表

| 参数 | 值 | 
| :-- | :-- |
| start | 页码，不传，默认为0 |
| per_page | 每页数据条数, 不传，默认为25 |
| flat | 如果为1， 返回stars数据，不包含目录结构 |
| pid | 指定目录下的stars数据，如果不传、或者传0，为跟目录下的数据 |
| q | 会按照搜索来过滤 |
   
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

### 4. Star一个Github项目

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| PUT | https://gitstars.cn/stars/github/{:user}/{:name}.json |

* 参数描述

| 参数关键字 | 是否可选 | 格式 | 描述 |
| :-- | :-- | :-- | :-- |
| {:user/:name} | 必选 | string | github项目的标识 |
| pid | 可选 | int | 直接放入某一个文件夹 |

* 返回结果

    + 请求成功

        响应码返回结果为 204， emtpy body

    + 请求失败

        响应码为 300以上

### 5. Unstar一个Github项目

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| DELETE | https://gitstars.cn/stars/github/{:user}/{:name}.json |

* 参数描述

| 参数关键字 | 格式 | 描述 |
| :-- | :-- | :-- |
| {:user/:name} | string | github项目的标识 |

* 返回结果

    + 请求成功

        响应码返回结果为 204， emtpy body

    + 请求失败

        响应码为 300以上

### 6. star操作接口

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| POST | https://gitstars.cn/stars.json |

* 参数描述

| 参数关键字 | 格式 | 描述 |
| :-- | :-- | :-- |
| a | "create_folder"/"delete_folder"/"move_folder"/"move" | 操作标识 |
| pid | int | 文件夹id |
| name | string | 文件夹名称create_folder和move_folder都可带这个参数 |
| github | :user/:name的格式，例如google/android | github项目标识 |
| new_pid | int | 新的文件夹id, move_folder 可用 |

### 7. 获取所有目录接口

* 接口定义

| 请求方法 | 接口定义 |
| :-- | :-- |
| GET | https://gitstars.cn/stars/folders.json |
