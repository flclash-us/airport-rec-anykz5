# Hosts 文件配置完全指南

Hosts 文件是最原始的域名解析方式，可用于绕过 DNS 污染、加速访问。

## Hosts 文件位置

| 系统 | 路径 |
|------|------|
| Windows | `C:\Windows\System32\drivers\etc\hosts` |
| macOS / Linux | `/etc/hosts` |
| Android | `/system/etc/hosts` (需Root) |

## 常用 Hosts 配置

### 加速 Google 服务

```
203.208.46.200  www.google.com
203.208.46.200  google.com
203.208.46.200  accounts.google.com
142.250.80.46  www.youtube.com
```

### GitHub 加速

```
140.82.113.4    github.com
140.82.112.3    api.github.com
185.199.108.153  raw.githubusercontent.com
```

### 绕过 DNS 污染

```
104.244.42.1    twitter.com
157.240.1.35    facebook.com
```

## 自动更新 Hosts

使用 [SwitchHosts](https://github.com/oldratlee/useful-scripts) 定时更新：

```yaml
title: Google Hosts
url: https://raw.githubusercontent.com/googlehosts/hosts/master/hosts-files/google-hosts
auto: true
```

## 广告 Hosts

```
0.0.0.0  ad.doubleclick.net
0.0.0.0  ads.google.com
0.0.0.0  pagead2.googlesyndication.com
```

## 常见问题

**Hosts 不生效？** Windows 下清除 DNS 缓存：`ipconfig /flushdns`

**macOS 不生效？** `sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder`

---

推荐工具：

- [Clash for Windows](https://clashforwindows.site/)
- [ClashMI](https://clashmi.site/)
- [FlClash](https://flclash.us/)
