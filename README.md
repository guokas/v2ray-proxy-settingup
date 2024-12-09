# Prerequisites
1. 域名
2. VPS

# 资料
1. 安装x-ui(内集成v2ray) [Installation Guide](install%20x%20ui/README.md)
2. 签发域名的SSL证书 [Installation Guide](Install%20Certificates%20For%20Nginx/README.md)
3. 利用nginx伪装v2ray  [Installation Guide](nginx-with-v2ray/README.md)

# 设置WSL使用V2ray的代理
```
```
https://stackoverflow.com/questions/78354196/how-to-use-v2rayn-in-windows-wsl2-ubuntu

# 设置v2ray代理github
```
# 设置代理，http 和 https 都加上代理，代理到 http://127.0.0.1:10808 这个 vpn 本地 IP
git config --global http.proxy http://127.0.0.1:10808
git config --global https.proxy http://127.0.0.1:10808

# 取消代理
git config --global --unset http.proxy
git config --global --unset https.proxy

# 查看代理
git config --global --get http.proxy
git config --global --get https.proxy

# 查看全局所有配置
git config --global --list
```
