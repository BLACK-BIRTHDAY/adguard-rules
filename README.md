# AdGuard Home Rules (NOIR Telemetry & Privacy Blocklist)

针对 Android 设备（特别是搭载 ColorOS / 一加 / OPPO 系列固件，经 [NOIR](https://github.com/Verlintas/NOIR) 审计提取）定制的 AdGuard Home 订阅规则。

在切断系统级广告与第三方埋点遥测的同时，**深度保护 Google 核心服务（GMS / Play 商店 / YouTube / Google Photos 等）与日常关键业务（微信、高德定位等）正常运行**。

## 订阅链接 (Subscription URLs)

在 **AdGuard Home** 控制台（`http://127.0.0.1:3000`）中，进入 **过滤器 (Filters)** -> **DNS 封锁清单 (DNS blocklists)** -> **添加阻止列表 (Add blocklist)** -> **添加一个自定义列表 (Add a custom list)**。

### 1. GitHub 官方直连地址
```text
https://raw.githubusercontent.com/BLACK-BIRTHDAY/adguard-rules/main/noir-blocklist.txt
```

### 2. 国内 CDN 加速镜像（国内直连推荐，防 DNS 污染）
```text
https://cdn.jsdelivr.net/gh/BLACK-BIRTHDAY/adguard-rules@main/noir-blocklist.txt
```
备用镜像：
```text
https://raw.gitmirror.com/BLACK-BIRTHDAY/adguard-rules/main/noir-blocklist.txt
```

---

## 规则分类说明

1. **Google 服务放行白名单**：通过 `@@` 语法保护 `googleapis.com`、`google.com`、`gstatic.com`、`youtube.com` 等关键通信。
2. **ColorOS / 欢太广告与遥测**：拦截 `*.ads.heytapmobi.com`、`*.wanyol.com`（玩友测试）、`*.finzfin.com`、Breeno 小布等内部遥测。
3. **第三方统计与崩溃上报**：拦截字节跳动/火山引擎（`*.snssdk.com`、`*.volces.com`）、友盟、阿里 UC/夸克埋点、腾讯 Bugly/Aegis、百度遥测等。
4. **App 专有埋点**：过滤什么值得买、滴滴等应用内嵌的数据回传。
