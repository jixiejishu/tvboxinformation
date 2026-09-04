# 常用TVbox-fongmi接口以及影音网站汇总

<img width="1280" height="720" alt="常见软件介绍关系2026" src="https://github.com/user-attachments/assets/9badaa50-eb41-4353-a589-ebde86917b7a" />

# 常用接口与软件下载

[https://github.com/jixiejishu/tvboxinformation/blob/main/详细资料.md](https://github.com/jixiejishu/tvboxinformation/blob/main/详细资料.md  "详细资料")   

---------------------------------------
# 导航网页
cloudfire  
[https://jxjs.jxjs888666.top/](https://jxjs.jxjs888666.top  "常用软件汇总")    
  
备用网址
[https://tvbox.jxjs888666.top](https://tvbox.jxjs888666.top "常用软件汇总")   
    
备用导航网页  
[https://tvboxpage.jxjs888666.top  ](https://tvboxpage.jxjs888666.top   "备用导航网页")   


-------------------------------

# 网络搜集 影视TVbox接口  
## 1.1  多线路接口：  
https://gh-proxy.org/https://raw.githubusercontent.com/jixiejishu/tvboxinformation/main/tvboxtools/jk/dxl/T%26S.txt  
https://gh.xxooo.cf/https://raw.githubusercontent.com/jixiejishu/tvboxinformation/main/tvboxtools/jk/dxl/T%26S.txt  
https://cdn.jsdelivr.net/gh/jixiejishu/tvboxinformation@main/tvboxtools/jk/dxl/T%26S.txt  

gitlab  
https://gitlab.com/jixiejishu/tvboxinformation/-/raw/main/tvboxtools/jk/dxl/T&S.txt  

酷云  
https://fastlink.cokey.xyz/f/RNBYso/T&S.txt  



## 1.2  多仓库接口：  
https://gh-proxy.org/https://raw.githubusercontent.com/jixiejishu/tvboxinformation/main/tvboxtools/jk/dck/duo.txt  
https://gh.xxooo.cf/https://raw.githubusercontent.com/jixiejishu/tvboxinformation/main/tvboxtools/jk/dck/duo.txt  
https://cdn.jsdelivr.net/gh/jixiejishu/tvboxinformation@main/tvboxtools/jk/dck/duo.txt  

gitlab  
https://gitlab.com/jixiejishu/tvboxinformation/-/raw/main/tvboxtools/jk/dck/duo.txt   
酷云  
https://fastlink.cokey.xyz/f/EQJQIX/duo.txt  


## 1.3 单线路  
https://gh-proxy.org/https://raw.githubusercontent.com/jixiejishu/tvboxinformation/main/tvboxtools/jk/dan/单线路.txt  
https://gh.xxooo.cf/https://raw.githubusercontent.com/jixiejishu/tvboxinformation/main/tvboxtools/jk/dan/单线路.txt  
https://cdn.jsdelivr.net/gh/jixiejishu/tvboxinformation@main/tvboxtools/jk/dan/单线路.txt    

gitlab  
[https://gitlab.com/jixiejishu/tvboxinformation/-/raw/main/tvboxtools/jk/dan/单线路.txt](https://gitlab.com/jixiejishu/tvboxinformation/-/raw/main/tvboxtools/jk/dan/单线路.txt  "网络搜集")  

酷云  
[https://fastlink.cokey.xyz/f/OVeRsM/%E5%8D%95%E7%BA%BF%E8%B7%AF.txt  ](https://fastlink.cokey.xyz/f/OVeRsM/%E5%8D%95%E7%BA%BF%E8%B7%AF.txt  "网络搜集")  






--------------------------------



# TVBox Fongmi 接口源说明

## 1. 文件调用路径

本地位置调用，路径指向本地，有两种方式。

### 1.1 相对路径

文件所属的文件夹可以放到本地任意位置，调用路径是相对的。

- 示例：

  ```json
  "ext": "./js/路漫漫.js"
  ```

- 用途：
  - **本地接口**：大多数本地包配置文件内的文件调用，可以直接放到支持的网络平台当在线接口用，比如 git 平台或者支持直链的网盘。
  - **在线接口**：配置文件和相应文件放到支持的网络平台上就是在线接口。

### 1.2 绝对路径

文件必须放到指定本地位置，调用文件是固定的。通常使用软件支持的固定格式和位置，或者特定端口。

- 示例：jar 的路径调用 `http://127.0.0.1:9978/` 是本地位置

  ```json
  "jar": "http://127.0.0.1:9978/file/TVBox/jar/spider.jar",
  "api": "csp_Market",
  "ext": "https://plum.now61.cn/f/ZWguY/bdgx.txt"
  ```

  线路的调用位置（原版影视可能不支持，OK 版支持两种）：

  ```text
  clan://localhost/TVBox/lib/无忧TV.json
  ```

  ```json
  {"url": "file://Pg/jsm.json", "name": "Pg线路"}
  ```

- 用途：
  - **A. 本地包内文件调用**：极少见，不能直接放到网络平台当在线接口用。目前仅有云星日记 / 无忧接口的本地包是这种格式。
  - **B. 本地单线路、多线路（单仓库）、多仓库的调用路径**。

### 1.3 网络路径

文件调用使用网址。

- 示例：
  - 配置文件：

    ```json
    {
      "key": "版本信息",
      "name": "版本 • 信息",
      "type": 3,
      "api": "csp_Market",
      "searchable": 0,
      "changeable": 0,
      "indexs": 0,
      "ext": "https://9877.kstore.space/single.json"
    }
    ```

  - 在线接口：`http://www.饭太硬.cc/tv`

- 用途：
  - 配置文件内的文件调用
  - 单线路配置文件、多线路（单仓库）、多仓库的网络调用路径
  - 本地多线路（单仓库）、多仓库的网络调用路径

---

## 2. 不同类型的接口

### 2.1 站点

接口最小的组成部分。一般是指向某个网站平台，名称由此而来。但实际上可以是很多内容按照一定分类组成的集合体。

有两类特殊的站点：

- **网盘站点**：需要自己注册网盘账号，通过扫码或者输入账号信息使用。
- **B 站站点**：把自己的账号信息输入进去实现完整功能。

- 示例：

  ```json
  {
    "key": "yqkan",
    "name": "影视|一起",
    "type": 3,
    "api": "csp_YQKan",
    "searchable": 1,
    "quickSearch": 1,
    "filterable": 0,
    "ext": "公众号:影视资源站"
  }
  ```

### 2.2 ZB

接口内独立的模块，可以本地或者网络文件。tvbox 的 ZB 文件格式事实上形成了一种标准文件格式（另一种是 DIYP 使用的格式）。

- 字段：`lives:[]`，按照线路类型划分。

### 2.3 单线路

主 jar（纯独立 py 可以没有）、若干站点、解析、ZB 模块（ZB 不是必须的）组合而成，使用一个单线路配置文件调用。单线路调用的配置文件可以在本地或者放到网络调用使用。

- 典型支持的软件：Q 版 tvbox 和 T 版 tvbox。

### 2.4 多线路（单仓库）

配置文件调用多个单线路的配置文件。多线路调用的配置文件可以在本地或者放到网络调用使用。

- 典型支持的软件：影视、影视仓、星落。

### 2.5 多仓库

多个单线路组成（很多时候会把单仓也叫多仓库，这是不同人对多仓定义不同导致的）。调用文件在本地，不同的单仓在网络，通常是为了安全使用。

但很多时候被人拿来贩卖，因此有很多诟病，很多软件不支持多仓。配置文件调用多个单仓，多仓调用的配置文件可以在本地或者放到网络调用使用。

- 典型支持的软件：影视仓、多仓影视、jade、newbox。

### 2.6 配置文件与调用文件

- **单线路**：各个站点使用一个配置文件调用，内容的格式是 json。文件格式是任意格式，也可以没有格式。现在很多为了防盗用，使用了加密。主 jar 调用加了 MD5 校验，饭太硬的接口甚至加了软件包名校验，不在白名单的软件使用会导致软件崩溃。
- **多线路 / 多仓库**：也有一个配置文件，为了区别单线路的配置文件，本文称之为**调用文件**。

---

## 3. 本地包与在线接口

### 3.1 单线路

| 类型 | 说明 |
| --- | --- |
| **A. 纯本地包** | 配置文件在本地，站点调用的文件大部分在本地 |
| **B. 半本地包** | 配置文件在本地，站点调用的文件部分本地部分网络 |
| **C. 网络调用包** | 配置文件在本地，调用站点都在网络 |
| **D. 在线接口** | 配置文件和调用站点都在网络，使用网址调用。配置文件和调用站点可以在同一位置，也可以是不同网络混合调用。大部分在线接口都是大部分站点调用同一位置的文件，部分调用其他位置的文件 |

### 3.2 多线路（单仓库）

| 类型 | 说明 |
| --- | --- |
| **A. 纯本地包** | 多线路调用文件在本地，调用的单线路都是纯本地包 |
| **B. 混合本地包** | 多线路调用文件在本地，调用的单线路部分是纯本地，部分是半本地 / 网络调用本地包 / 在线接口 |
| **C. 网络接口** | 多线路调用文件在网络，使用网址调用。可以与一个或者几个线路在同一个位置，也可以异地位置 |

### 3.3 多仓库

由于不同的单仓通常是同一个内容，因此很少有完整的多仓本地包。

| 类型 | 说明 |
| --- | --- |
| **A. 本地调用网络多仓库文件** | 多仓调用文件在本地，调用网络单仓 |
| **B. 在线接口** | 多仓库调用文件在网络，使用网络地址调用。单仓在不同的位置，多仓配置文件可以与其中一个单仓在相同位置，也可以是异地位置 |

### 3.4 混合调用

- **A. 本地混合调用**：不同的本地调用文件和本地线路放在一个本地文件内，通过不同的在线、本地组合形成。可以调用单仓、多线路、多仓。典型：云星日记 / 无忧本地包。
- **B. 在线混合调用**：不同的调用文件配置文件和站点文件放在一个网络平台上，通过不同的文件调用本地异地文件，站点可以调用本地或者异地内容。可以调用单仓、多线路、多仓。典型：高天流云。

### 3.5 典型的本地包

- **奇奇**（纯本地）
- **云星日记 / 无忧本地包**（混合本地包）
- **潇洒**（可以在线更新）
- **欧歌**（配置文件调用在线站点）

---

## 4. 接口源

### 4.1 Java 源

Java 编写的源，tvbox 最基本的源。

- **特点**：api 以 `csp_` 开头，主要功能是在 jar 里，jar 配置在接口的 spider 字段或者站点的 jar 字段。封装在 jar 内，是主流的格式，不能直接查看内容，修改编写难度大。主 jar 也是 java 源，以前的接口必须有 jar。
- **样例**：

  ```json
  {
    "key": "yqkan",
    "name": "影视|一起",
    "type": 3,
    "api": "csp_YQKan",
    "searchable": 1,
    "quickSearch": 1,
    "filterable": 0,
    "ext": "公众号:影视资源站"
  }
  ```

### 4.2 py

Python 编程的爬虫文件。

- **特点**：api 以 `py_` 开头，主要功能在 ext 引用的 py 文件里。部分需要使用 jar，部分可以单独使用。PeekPro 可以直接调用不依赖 jar 的 py 文件。独立的 py 源可以组成接口。
- **样例**（海豚常规接口没有 jar，主要是 py 源，部分独立的 js 源）：

  ```json
  {
    "key": "py_m1905",
    "name": "M1905",
    "type": 3,
    "api": "./py/1905.py",
    "searchable": 0,
    "quickSearch": 0,
    "filterable": 0
  }
  ```

### 4.3 js 源

JavaScript 编写的文件。

- **特点**：api 中包含 `drpy` 或者 `drpy2`，主要功能在 ext 引用的 js 文件里。部分 js 文件不需要调用 jar，需要调用一个主文件，主要是道长的项目生产的 js。
  - 2025 年年初的 js 版本是最后的 js 版本，后面的 jar 不再支持道长新的 js 项目了。
  - 2026 版的道长只有少量的 js 文件和少量 py 文件可以使用。
- **样例**：

  ```json
  {
    "key": "畅梦",
    "name": "畅梦┃秒播",
    "type": 3,
    "api": "./js/lib/drpy2.min.js",
    "ext": "./js/changmeng.js"
  }
  ```

### 4.4 采集接口

不需要使用爬虫，直接调用采集网站的接口。

- 大部分采集网站都有切片广告或者跑马灯广告，广告内容多是博彩，外号**菠菜源**。
- 大部分采集接口内还包含伦理内容，需要使用字段进行屏蔽。
- **样例**：

  ```json
  {
    "key": "种子短剧",
    "name": "短剧┃视频",
    "type": 1,
    "api": "http://zzdj.cc/api.php/provide/vod"
  }
  ```

### 4.5 参考

- 参考网站：https://mp.weixin.qq.com/s?__biz=MzIzODAyMjIyNg==&mid=2653519930&idx=1&sn=e1ed3ad7f1a90ff0e957c8b97f062861&chksm=f2e29b07c59512118db41d5f2d5b2ee61c981cbb71940da2f95e980839c6a1932879379bd1ee&scene=178&cur_album_id=3254209826616754181&search_click_id=#rd

---

## 5. 特殊情况

### 5.1 云星日记

本地包的单线路配置文件调用使用了绝对路径，使用了 `http://127.0.0.1:9978/` 的绝对路径调用，不能放到网络上直接当在线接口使用。

### 5.2 海豚

常规接口主要是 py 和部分 js，没有 jar。

### 5.3 欧歌

接口自适应：在影视上是多线路，在影视仓等多仓软件上是多仓库。欧歌接口内每个单线路都是只有一个配置文件，每个单线路配置文件所有的调用都是网络调用。jar、站点、ZB 文件都是使用的网络内容。

### 5.4 片库

这个软件不支持多线路和多仓，会把线路拆成一个个的站点。

### 5.5 潇洒

利用 fongmi 提供的 jar 的应用商店功能，下载并解压网络存储的本地包，实现本地包在线更新功能。目前有此功能的本地包有：云星日记 / 无忧、欧歌。
