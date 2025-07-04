# Solve-the-problem-that-Docker-still-cannot-pull-images-after-configuring-the-proxy-in-China
在保证代理配置无误的情况下（curl www.google.com），手动配置dockerhub镜像
1.修改文件vim /etc/docker/daemon.json 没有则新建
{
 "registry-mirrors": [
    "https://hub.docker.com/"]
}

这下就能愉快的拉取镜像了~
![微信图片_2025-07-04_093019_153](https://github.com/user-attachments/assets/0a65fed6-c23b-492b-b8e9-c94392aa146f)

配置代理：
1.修改文件 vim /etc/systemd/system/docker.service.d/proxy.conf
[Service]
Environment="HTTP_PROXY=http://XXX:XXXX"
Environment="HTTPS_PROXY=http://XXX:XXXX" 

2.
# 加载配置
systemctl daemon-reload
# 重启docker
systemctl restart docker
