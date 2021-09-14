# 域名DNS配置 https://dash.cloudflare.com/
# v2ray配置教程 https://toutyrater.github.io/basic/vmess.html

# 设置linux系统时间为北京时间
```
// 1.删除自带的localtime
rm -rf /etc/localtime
// 2.创建软链接到localtime
ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

```

# 安装 参考官方： https://github.com/v2fly/fhs-install-v2ray
```
bash <(curl -L https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-dat-release.sh)

systemctl enable v2ray

systemctl start v2ray
```

# 配置
```
cd /usr/local/etc/v2ray/

// 下载配置文件
curl -O https://raw.githubusercontent.com/kk37005/V2rayPemKey/master/v2ray-config/config.json

ls /usr/local/etc/v2ray/

mv /usr/local/etc/v2ray/config.json /usr/local/etc/v2ray/config.json.back4

cp v2ray-config/config.json /usr/local/etc/v2ray/

systemctl restart v2ray
```
