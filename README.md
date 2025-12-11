# OpenClash 自定义规则rule-providers配置说明

本仓库提供一套基于 **OpenClash** 的规则与 rule-providers 配置，你只需要 **更换订阅链接** 即可使用。整体结构与常见公共规则兼容，核心部分参考 **Dler Cloud** 的规则，并在此基础上根据实际需求做了补充与调整。

---

## 📌 使用方式

1. **替换订阅链接**
   将你的 Clash 或 OpenClash 订阅填入配置文件中即可正常加载。

2. **直接引用 RAW 链接**
   `raw.githubusercontent.com/s11214/rules/main/rule_providers`
   因此修改规则内容无需重新上传，直接在 GitHub 上保存即可生效。

---

## 📁 规则来源与结构

### 主体规则

大部分规则基于 **Dler Cloud 规则集**，涵盖：

* 广告屏蔽
* 国内站点
* 国内媒体
* 国际媒体
* 常用代理规则
* 等常规分类

### 我额外补充的分类（根据个人业务需求）

* **Domestic Media**
  国内第三方视频网站相关域名（如：影视 APP/CDN/加速节点）。

* **Other Direct / Other Proxy**
  属于自定义业务流量，根据自身网络分流场景创建。

* **Single Server Proxy One / Two / Three**
  单节点业务流量分流，用于指定特定任务直走某一代理节点。

* **Multi Server Proxy**
  多节点轮询 / 聚合出口，用于一些需要不同出口 IP 的任务。

---

## 📦 rule_providers 说明

所有 rule provider 文件位于：

```
rule_providers/
```

示例引用方式：

```yaml
miHoYo:
  type: http
  behavior: classical
  url: https://raw.githubusercontent.com/s11214/rules/main/rule_providers/miHoYo.yaml
  path: ./Rules/miHoYo
  interval: 86400
```

---

## 🛠 自定义内容

为适配个人网络结构、服务与数据源，加入包括但不限于：

* CDN 域名补全
* 特定 API 的代理/直连规则
* 各业务平台的访问行为优化
* 自用设备专属出口策略

这些扩展不会影响基础规则集的完整性，只增强灵活度。

---

## 🚀 如何更新

* 你可以直接在 GitHub 上修改规则文件（YAML）
* RAW 链接会让 OpenClash 自动读取最新内容
* 无需重新上传或打包

