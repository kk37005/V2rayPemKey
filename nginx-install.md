# 安装环境
```
yum install -y vim

yum install -y wget

yum install -y gcc

yum install -y pcre pcre-devel

yum install -y zlib zlib-devel

yum install -y openssl openssl-devel

```

# 下载 nginx
```
wget -c https://nginx.org/download/nginx-1.15.0.tar.gz
tar -zxvf nginx-1.15.0.tar.gz
cd nginx-1.15.0
```

# 安装 nginx
```
./configure --prefix=/usr/local/nginx --with-http_stub_status_module --with-http_ssl_module

make

make install
```

# 切换到/usr/local/nginx安装目录
```
cd /usr/local/nginx

cd config

// 修改配置
vim nginx.conf

cd sbin

// 启动
./nginx

// 强制停止
./nginx -s stop

// 平滑停止
./nginx -s quit

// 平滑重启
./nginx -s reload

// 查看是否启动成功
ps -ef | grep nginx

```

# 开机自启动
```
vim /etc/rc.local

// 增加一行 
/usr/local/nginx/sbin/nginx

// 设置执行权限：
chmod 755 rc.local
```

# 添加签名
```
cd /root

mkdir cert

cd cert

curl -O https://raw.githubusercontent.com/kk37005/V2rayPemKey/master/cert.key

curl -O https://raw.githubusercontent.com/kk37005/V2rayPemKey/master/cert.pem


```