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

systemctl restart v2ray
```
