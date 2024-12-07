# 安装X-ui
```
#更新软件源
apt update
#启用 BBR TCP 拥塞控制算法
echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
sysctl -p

# 安装x-ui：
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```

## 管理x-ui
```
# 启动x-ui
x-ui

# 启动x-ui,设置根目录，端口，然后通过ip:端口访问，例如：localhost:8080/xui
```

# Issues:
if encounter error 
```
bash: /proc/self/fd/11: No such file or directory
```
then changes to run:
```
bash < <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```
