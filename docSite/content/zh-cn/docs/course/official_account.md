---
title: '接入微信公众号教程'
description: 'FastGPT 接入微信公众号教程'
icon: 'description'
draft: false
toc: true
weight: 113
---

从 4.8.10 版本起，FastGPT 商业版支持直接接入微信公众号，无需额外的 API。

**注意⚠️: 目前只支持通过验证的公众号（服务号和订阅号都可以）**

## 1. 在 FastGPT 新建发布渠道

在 FastGPT 中选择想要接入的应用，在 *发布渠道* 页面，新建一个接入微信公众号的发布渠道，填写好基础信息。

![图片](/imgs/offiaccount-1.png)

## 2. 登录微信公众平台，获取 AppID 、 Secret和Token

### 1. https://mp.weixin.qq.com 登录微信公众平台，选择您的公众号。

**只支持通过验证的公众号，未通过验证的公众号暂不支持。**

开发者可以从[这个链接](https://mp.weixin.qq.com/debug/cgi-bin/sandbox?t=sandbox/login)申请微信公众号的测试号进行测试，测试号可以正常使用，但不能配置 AES Key

![图片](/imgs/offiaccount-2.png)

### 2. 把3个参数填入 FastGPT 配置弹窗中。
![图片](/imgs/offiaccount-3.png)

## 3. 在 IP 白名单中加入 FastGPT 的 IP

![图片](/imgs/offiaccount-4.png)

填写后，可能需要几分钟后才生效，未生效时，问题会正常发送和回答，但是无法在公众号中查看到（可以在对话日志里查看）

私有部署的用户可自行查阅自己的 IP 地址。

海外版用户（fastgpt.in)可以填写下面的 IP 白名单：

```
34.87.20.17
35.247.161.35
34.87.51.146
34.87.110.152	
35.247.163.68
34.126.163.205
34.87.20.189
34.87.102.86
35.240.227.100
35.198.192.104
34.143.149.171
34.87.152.33
34.124.237.188
35.197.149.75
34.87.44.74
34.124.189.116
34.87.79.202
34.87.173.252
34.143.240.160
34.87.180.104
34.142.157.52
```

## 4. 获取AES Key，选择加密方式

![图片](/imgs/offiaccount-5.png)

![图片](/imgs/offiaccount-6.png)

1. 随机生成AESKey，填入 FastGPT 配置弹窗中。

2. 选择加密方式为安全模式。

## 5. 获取 URL

1. 在FastGPT确认创建，获取URL。

![图片](/imgs/offiaccount-7.png)

2. 填入微信公众平台的 URL 处，然后提交保存
![图片](/imgs/offiaccount-8.png)

## 6. 启用服务器配置（如已自动启用，请忽略）
![图片](/imgs/offiaccount-9.png)

## 7. 开始使用

现在用户向公众号发消息，消息则会被转发到 FastGPT，通过公众号返回对话结果。