docker-sync工具用来同步卷数据，win10家庭版下未能用成功

docker for Windows的安装要开启Hyper-V

win10家庭版没有Hyper-V,Hyper-V也不能独立安装！！！= =

不想升级到专业版（各种原因），只能退而求其次，安装DockerToolBox

docker镜像加速：

1.docker-machine ssh default

2.sudo sed -i "s|EXTRA_ARGS='|EXTRA_ARGS='--registry-mirror=https://registry.docker-cn.com |g" /var/lib/boot2docker/profile

3.exit

4.docker-machine restart default

用docker info命令查看是否配置成功

环境win10，一个坑：invalid volume specification

解决：在.env增加一行：COMPOSE_CONVERT_WINDOWS_PATHS=1