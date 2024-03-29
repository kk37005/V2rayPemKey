# 安装环境
```
yum install -y vim

yum install -y wget

yum install net-tools

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
// 设置 nginx 全局访问
ln -s /usr/local/nginx/sbin/nginx /usr/local/bin/

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

# 配置
```
cd /usr/local/nginx/conf

mv nginx.conf nginx.conf.b1

// 下载配置文件
curl -O https://raw.githubusercontent.com/kk37005/V2rayPemKey/master/nginx.conf

../sbin/nginx -s reload

// function 2

ls /usr/local/nginx/conf

mv /usr/local/nginx/conf/nginx.conf /usr/local/nginx/conf/nginx.conf.b2

cp nginx.conf /usr/local/nginx/conf

/usr/local/nginx/sbin/nginx -s reload
```
