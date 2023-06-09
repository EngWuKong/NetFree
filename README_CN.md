# 官方文档

https://github.com/shadowsocks/shadowsocks-libev/blob/master/docker/alpine/README.md


# 简明指导
1. 创建 
```docker-compose.yml```, 建议创建一个专有目录存放配置文件. 如  ``` ~/shadowsocket/config```
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
建议修改: "8388:8388" 中 冒号前面的端口,不要修改冒号后面的端口<br>
必须修改: PASSWORD_SECRET