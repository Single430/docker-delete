# docker-delete  docker 仓库镜像删除脚本

> 先下载脚本到/usr/local/bin/目录下
```
curl https://raw.githubusercontent.com/hushuai86/docker-delete/master/docker-delete-2.0.sh | sudo tee /usr/local/bin/docker-delete >/dev/null
```

> 赋予可执行权限
```
chmod a+x /usr/local/bin/docker-delete
```

> 私有库镜像存储目录路径全局环境变量（该路径就是运行私有库容器时，用-v 命令将私有库容器内 /var/lib/registry目录挂载到本机的路径）
```
#例： /opt/data/registry是我运行容器时私有库镜像存储目录挂载到本地的目录
echo "export DOCKER_REGISTRY_DIR=/opt/data/registry" >>/etc/profile
```

> 运行私有库容器ID全局环境变量设置（正在运行的私有库容器的 ID）
```
#例： 89b9b3c9054ay是我的私有库库容器的id
echo "export DOCKER_REGISTRY_CONTAINER_ID=89b9b3c9054a" >>/etc/profile
```

> 使配置生效
```
source /etc/profile
```
