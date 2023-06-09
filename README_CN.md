# 官方文档

https://github.com/shadowsocks/shadowsocks-libev/blob/master/docker/alpine/README.md


# 简明指导
1. 创建 
```docker-compose.yml```, 建议创建一个专有目录存放配置文件.
 <br>如  ``` ~/shadowsocket/config```
2. 添加配置内容
```
shadowsocks:
  image: shadowsocks/shadowsocks-libev
  ports:
    - "8388:8388"
  environment:
    - METHOD=aes-256-gcm
    - PASSWORD_SECRET=shadowsocks
  secrets:
    - shadowsocks
```

![注意](/attchment/shadowsocks_config.png =100)

3. 
```
cd ~/shadowsocket/config
curl -sSLO https://github.com/shadowsocks/shadowsocks-libev/raw/master/docker/alpine/docker-compose.yml
docker-compose up -d
docker-compose ps
```

4. 注意 VPS 或 主机开放第2步中端 第一个端口<br>
以 AWS 为例:
![Alt text](/attchment/AwsNetWorkSecurityGroupConfig.png =100)