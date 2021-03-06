# V2Ray Heroku

## 概述

用于在 Heroku 上部署 V2Ray Websocket。

网址：https://id.heroku.com/login

**Heroku 为我们提供了免费的容器服务，我们不应该滥用它，所以本项目不宜做为长期翻墙使用。**

**可以部署两个以上的应用，实现[负载均衡](https://toutyrater.github.io/app/balance.html)，避免长时间大流量连接某一应用而被 Heroku 判定为滥用。**

**Heroku 的网络并不稳定，部署前请三思。**

## 镜像

本镜像仅 6MB，比起其他用于 Heroku 的 V2Ray 镜像，不会因为大量占用资源而被封号。

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new-app?template=https://github.com/yeahwu/v2ray-heroku)

## ENV 设定

### UUID

`UUID` > `一个 UUID，供用户连接时验证身份使用`。

## 注意

WebSocket 路径为 /。

AlterID 为 64。

80端口和443端口都可以使用，80端口速度普遍比443端口略快；443端口需要打开TLS，比80端口较安全。

服务端开启了DoH，本地客户端DNS服务器可选择`https://1.1.1.1/dns-query,https://rubyfish.cn/dns-query,https://dns.alidns.com/dns-query`这个是可选项，客户端可不做修改。

V2Ray 将在部署时自动安装最新版本。

**出于安全考量，除非使用 CDN，否则请不要使用自定义域名，而使用 Heroku 分配的二级域名，以实现 V2Ray Websocket + TLS。**
