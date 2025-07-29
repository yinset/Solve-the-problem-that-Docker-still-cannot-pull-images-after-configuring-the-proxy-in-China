# Linux Docker在使用魔法时依旧无法拉取的解决方案;docker pull使用代理后仍无法拉取
在保证代理配置无误的情况下进行（curl www.google.com）

手动配置dockerhub镜像


1.修改文件

vim /etc/docker/daemon.json    没有则新建


{
 "registry-mirrors": [
    "https://hub.docker.com/"]
}

重启docker
sudo systemctl daemon-reload
sudo systemctl restart docker
sudo service docker restart

这下就能愉快的拉取镜像了~


![微信图片_2025-07-04_093019_153](https://github.com/user-attachments/assets/0a65fed6-c23b-492b-b8e9-c94392aa146f)

