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

# Issues:
if encounter error 
```
bash: /proc/self/fd/11: No such file or directory
```
then changes to run:
```
bash < <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```
