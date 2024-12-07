# Prerequisites
1. 域名
2. VPS

# 步骤
1. 安装x-ui(内集成v2ray) [Installation Guide](install%20x%20ui/README.md)
2. 签发域名的SSL证书 [Installation Guide](Install%20Certificates%20For%20Nginx/README.md)
3. 利用Nginx伪装v2ray

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
