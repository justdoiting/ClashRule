订阅转换教程

---
直接现成用法：
（1）打开https://sub.v1.mk
（2）填写自己的订阅链接
（3）远程配置选择emby-TikTok-流媒体分组去广告加强版
（4）点击 生成订阅链接
（5）将生成的订阅链接导入clash的配置中
![image](https://user-images.githubusercontent.com/109136320/179713465-25c87cfe-39eb-49e8-b829-c4293f418b63.png)



1. 选择订阅转换服务器

- 用别人搭建好的（因为前端一般不支持自定义后端故以下仅作前端推荐）
  - 肥羊：
    https://sub.v1.mk/
  - acl4ssr
    https://acl4ssr-sub.github.io/
- 也可自行搭建
  - 前端项目地址：
    https://github.com/youshandefeiyang/sub-web-modify
  - 后端项目地址：
    https://github.com/tindy2013/subconverter

---

2.订阅转换

以肥羊前端（https://sub.v1.mk ）为例，解释一下各个参数

- 订阅链接
  顾名思义就是把要转换的订阅（必须直接包含节点信息，用已经转换过的放进去套娃是识别不到的哦）放进去，可放多个（每行一个或用"|"符号分隔）
- 生成类型
  - clash
    - clash就选它，clash系和shadowrocket通用
    - clash系软件
      - Windows
        - Clash for Windows
      - Android
        - Clash for Android
      - IOS
        - Stach
        - Choc
      - macOS
        - ClashXPro
        - Clash for Windows
      - Liunx
        - Openwrt
          OpenClash
        - Others
          ShellClash
        - 待补充
  - 混合订阅（mixed）
    - 混合订阅的意思就是把各类型（包括Shadowsocks、V2ray、Trajon）的节点以纯节点信息然后base64加密的方式混在一起，V2ray系和shadowrocket都可用
  - 有待补充
- 后端地址
  一般只能选提供的后端无法自定义，这里推荐选择肥羊的后端，长期使用下来兼容性和稳定性可以说都是最好的
- 短链选择
  转换后的订阅地址为后端地址加一系列参数，URL一般较长不甚美观，故可转为短链接
- 远程配置
  - 分流配置，可以选择给定的也可以输入URL自定义分流规则（注意必须是直链才行），自用clash分流规则直链地址
    https://raw.githubusercontent.com/justdoiting/ClashRule/main/GeneralClashRule.ini
  - 自定义策略组
    - 选择模式
      - 延迟最低，顾名思义，每隔一段时间进行延迟测试，选择延迟最低的节点
      - 故障转移，每次都选组内第一个节点，无法使用再换到第二个，依次类推
      - 手动选择，顾名思义，没有特殊功能
      - 负载均衡，每个节点都用用，由于很多机场都有连接数的限制，因此实际使用较少
    - 节点筛选规则
      - 常用规则
        - 选择全部节点
          .*
        - 选择全部新加坡节点
          (新加坡|坡|狮城|SG|Singapore)
        - 待补充
  - 分流规则
    - 可直接写也可引用
      - 推荐引用为主
      - 常用引用仓库
        - ACL4SSR
          https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash
        - blackmatrix7
          https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash
    - 排序
      分流规则的匹配是按照至上而下收录，匹配到了就停止不再往下，比如YouTube规则要放在国外媒体前面，而完整的国外媒体规则包含了YouTube, Netflix, Pornhub等等，所以分流规则较大要放在YouTube小分流规则后面
    - 排序原则
      重要直连分流规则 > 去广告规则 > 小分流 > 国内外大分流 > 补充规则
- 高级功能
  - 包含节点
    - 节点黑名单，只有符合匹配规则的节点才会显示
    - 常用规则
      - 只用香港节点
        HK|香港|Hong Kong
      - 待补充
  - 排除节点
    - 节点白名单，符合匹配规则的节点会被筛掉
    - 常用规则
      - 将官网信息节点和流量信息节点筛掉
        官网|流量
      - 待补充
  - 节点命名
    节点按照一定规则重命名
  - 订阅命名
     订阅名称，在Clash for Windows一般会显示，其他客户端大多都为自定义
  - 更多选项（右下角）
    - Emoji
      默认开启
    - 启动UDP
      推荐开启
    - 启动TFO
      推荐开启
    - 待补充

---

3.参考示例


![填写](https://user-images.githubusercontent.com/109136320/179202130-e2dc2f82-7d4b-4c10-be32-52f3a3e4582b.png)


![我的分组规则](https://user-images.githubusercontent.com/109136320/179201756-5a457661-ca2d-4c0a-8031-d3b50fea4ff3.jpg)

