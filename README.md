# v2ray-proxy-settingup

# Prerequisites
1. 域名
2. VPS



# 签发域名的SSL证书
-> Install Certificates For Nginx -> README.me


# 将v2ray通过Nginx来伪装

# 安装 x-ui
## 命令
> x-ui
## 访问
启动x-ui,设置根目录，端口，然后通过ip:端口访问，例如：localhost:8080/xui



# 解决github代理问题

## 设置代理，http 和 https 都加上代理，代理到 http://127.0.0.1:1087 这个 vpn 本地 IP
```
git config --global http.proxy http://127.0.0.1:10809 
git config --global https.proxy http://127.0.0.1:10809
```

## 取消代理
```
git config --global --unset http.proxy
git config --global --unset https.proxy
```

## 查看代理
```
git config --global --get http.proxy
git config --global --get https.proxy
```

## 查看全局所有配置
```
git config --global --list
```
