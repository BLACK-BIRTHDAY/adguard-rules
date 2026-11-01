# AdGuard Home Rules (NOIR Multi-Device Privacy & Telemetry Blocklist)

针对 Android 手机与平板（经 [NOIR](https://github.com/Verlintas/NOIR) 审计提取，已适配 **ColorOS / 一加 / OPPO** 以及 **小米平板 / MIUI / HyperOS** 固件）定制的 AdGuard Home 订阅规则。

在切断系统底层广告联盟与第三方埋点遥测的同时，**深度保护 Google 核心服务（GMS / Play 商店 / YouTube / Google Photos 等）与日常关键业务（微信、高德定位、网盘等）正常运行**。

---

## 订阅链接 (Subscription URLs)

在 **AdGuard Home** 控制台（`http://127.0.0.1:3000`）中，进入 **过滤器 (Filters)** -> **DNS 封锁清单 (DNS blocklists)** -> **添加阻止列表 (Add blocklist)** -> **添加一个自定义列表 (Add a custom list)**。

### 1. 国内 CDN 加速镜像（国内直连推荐，防 DNS 污染/免代理）
```text
https://cdn.jsdelivr.net/gh/BLACK-BIRTHDAY/adguard-rules@main/noir-blocklist.txt
```

### 2. GitHub 官方直连地址
```text
https://raw.githubusercontent.com/BLACK-BIRTHDAY/adguard-rules/main/noir-blocklist.txt
```

### 3. 备用镜像
```text
https://raw.gitmirror.com/BLACK-BIRTHDAY/adguard-rules/main/noir-blocklist.txt
```

---

## 规则覆盖说明

### 1. 核心白名单放行（防误杀）
* **Google 体系放行**：通过 `@@` 语法保护 `googleapis.com`、`google.com`、`gstatic.com`、`youtube.com`、`googleusercontent.com` 等。
* **高频工具与地图放行**：放行 `mediafire.com`（Solid Explorer 等网盘工具）、`bing.com`、`amap.com`（高德地图基础定位）。

### 2. 小米平板 / MIUI / HyperOS 系统遥测（本次新增）
* **安全中心与隐私日志**：`*.sec.miui.com`、`*.sec.intl.miui.com`、`privacy.api.intl.miui.com`、信通院反诈接入接口 `eps.caict.ac.cn`、微智接口 `*.cloud.weizhi.com`。
* **小爱同学与视觉 AI 埋点**：`*.xiaomixiaoai.com`、`tracker-staging.ai.srv`、`tracker*.ai.xiaomi.com`。
* **搜索与推送统计**：`global.search.xiaomi.net`、`upload-data-api.xmpush.xiaomi.net`（注意：保留了核心推送通道 `api.xmpush.xiaomi.com`，避免影响第三方 App 正常推送收信）。

### 3. ColorOS / 一加系统遥测
* **欢太广告与测试上报**：`*.ads.heytapmobi.com`、`*.wanyol.com`（玩友测试）、`*.finzfin.com`、Breeno 小布内部接口等。

### 4. 通用第三方 SDK 与专有埋点
* **字节/火山引擎**：`*.snssdk.com`、`apmplus.volces.com`。
* **阿里/夸克/UC**：`*.applog.uc.cn`、`*.applog.lc.quark.cn`、`*.log.aliyuncs.com`。
* **搜狗输入法定制版**：`*.shouji.sogou.com`（封杀后台词库与行为上报）。
* **百度系日志**：`browserkernel.baidu.com`、`graph.baidu.com`、`blg.map.baidu.com`。
* **腾讯 Bugly & 地图轨迹**：`aegis.qq.com`、`bugtrace.3g.qq.com`、`rttgpsreport.map.qq.com`。
* **迅雷下载器统计**：`*.sandai.net`。
