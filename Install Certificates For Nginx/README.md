# Environment
```
DNS: Cloudflare
OS: Ubuntu
```


# 配置解析
1. 在Cloudflare 上 将域名解析到目标服务器

# 配置防火墙
```
1. 检查防火墙的状态
--确保80端口和443端口都是打开的
> sudo ufw status

2. 添加80,443端口
> sudo ufw allow 80
> sudo ufw allow 443
```

# Install Nginx
```1. 安装Nginx
> apt install Nginx

-- 2.检查Nginx 状态
> service nginx status
```

配置nginx 监听80端口

```
> cat /etc/nginx/nginx.conf
> sudo nano /etc/nginx/nginx.conf
```

添加如下配置到http节点下：
```
    server {
        listen 80;
        location /.well-known/ {
               root /var/www/html;
            }
        location / {
                rewrite ^(.*)$ https://$host$1 permanent;
            }
    }
```

# 使用Acme签发证书

官方文档： https://github.com/acmesh-official/acme.sh

```

--1. 安装acme
> cd ~
> curl https://get.acme.sh | sh -s email=my@example.com
> cd ~/.acme.sh
--显示Acme的帮助信息
> acme.sh -h

--2. 签发证书
> ./acme.sh --issue  -d "*.yourdomain.com"  -w /var/www/html  --debug
-- *.yourdomain.com 签发的证书对子域名也会起作用

-- 如果这一步显示Cannot init API for https://acme.zerossl.com/v2/DV90的话，可以换成letsencrypt
-- acme支持非常多的Provider(官方文档中有)， 由于zerossl是默认的，所以如果zerossl不行的话，可以用letsencrypt
-- 使用这个命令切换到letsencrypt: acme.sh --set-default-ca --server letsencrypt

--如果显示错误：Permission, Cannot write token to file: /var/www/html/.well-known/acme-challenge/B_1aySYouqI5ERuGCiVriWyzPi15ZA4m7AF2bQTZBEM 
--就是没有权限，运行：
--chmod +777 /var/www/html
--chmod +777 /var/www/html/.well-known/acme-challenge/

```

# 安装证书到Nginx
```
> ./acme.sh --installcert -d yourdomain.com --key-file /path/to/keyfile/in/apache/key.pem --fullchain-file /path/to/fullchain/certfile/apache/fullchain.pem --debug
```

# 配置自动更新证书
```
> ./acme.sh --upgrade --auto-upgrade
```

