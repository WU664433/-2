简介
本项目生成适用于Clash Premium 内核的规则集（RULE-SET），同时适用于所有使用 Clash Premium 内核的 Clash 图形用户界面（GUI）客户端。使用 GitHub Actions 北京时间每天早上 6:30 自动构建，保证规则最新。

说明
本项目规则集（RULE-SET）数据主要来源于项目@Loyalsoldier/v2ray-rules-dat和@v2fly/domain-list-community；Apple和Google列表里的域名来源于项目@felixonmars/dnsmasq-china-list；中国大陆 IPv4 地址数据使用@17mon/china_ip_list。

本项目的规则集（RULE-SET）仅适用于 Clash Premium版本。Clash Premium 相对于普通版，增加了TUN 增强模式，能接管设备所有 TCP 和 UDP 流量。

Clash Premium 各版本下载地址
⚠️由于 Clash 其部分周边生态项目于 2023 年 11 月上旬删库跑路，现提供部分官方原版安装包、可执行文件，详情见隐藏分支。

Clash Premium命令行版本：
官方版（适用于Windows、macOS、Linux、OpenWRT等多种平台）
衍生版 Clash.Meta（适用于Windows、macOS、Linux、OpenWRT 等多种平台）
Clash Premium图形用户界面版：
ClashN（适用于Windows）
ClashX Pro（适用于 macOS）
Clash-verge（适用于 Windows、macOS、Linux）
Clash for Windows（适用于 Windows、macOS、Linux）
Clash for Android（适用于Android）
规则文件地址及使用方式
在线地址（URL）
如果无法访问域名raw.githubusercontent.com，可以使用第二个地址（cdn.jsdelivr.net），但是内容更新会有 12 小时的延迟。以下地址填写在 Clash 配置文件里rule-providers的url配置项中。

直连域名列表 direct.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/direct.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/direct.txt
代理域名列表proxy.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/proxy.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/proxy.txt
广告域名列表reject.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/reject.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/reject.txt
私有网络专用域名列表 private.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/private.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/private.txt
Apple 在中国大陆可直连的域名列表 apple.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/apple.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/apple.txt
iCloud 域名列表 icloud.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/icloud.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/icloud.txt
[谨慎用]Google 在中国大陆可直连的域名列表 google.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/google.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/google.txt
GFWList 域名列表 gfw.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/gfw.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/gfw.txt
非中国大陆使用的顶级域名列表 tld-not-cn.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/tld-not-cn.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/tld-not-cn.txt
Telegram 使用的IP地址列表 telegramcidr.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/telegramcidr.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/telegramcidr.txt
陆地IP及保留IP地址列表lancidr.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/lancidr.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/lancidr.txt
中国大陆 IP 地址列表 cncidr.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/cncidr.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/cncidr.txt
需要直连的常见软件列表 applications.txt：
https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/applications.txt
https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/applications.txt
使 用 方 式
以供使用本项目的规则集，只需要在Clash配置文件中添加如下rule-providers和rules。

规则提供程序配置方式
rule-providers:
  reject:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/reject.txt"
    path: ./ruleset/reject.yaml
    interval: 86400

  icloud:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/icloud.txt"
    path: ./ruleset/icloud.yaml
    interval: 86400

  apple:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/apple.txt"
    path: ./ruleset/apple.yaml
    interval: 86400

  google:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/google.txt"
    path: ./ruleset/google.yaml
    interval: 86400

  proxy:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/proxy.txt"
    path: ./ruleset/proxy.yaml
    interval: 86400

  direct:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/direct.txt"
    path: ./ruleset/direct.yaml
    interval: 86400

  private:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/private.txt"
    path: ./ruleset/private.yaml
    interval: 86400

  gfw:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/gfw.txt"
    path: ./ruleset/gfw.yaml
    interval: 86400

  tld-not-cn:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/tld-not-cn.txt"
    path: ./ruleset/tld-not-cn.yaml
    interval: 86400
