# torchnet
some net implement by torchnet

# 创建Docker镜像

```
docker buildx build -t summit4you/cuda-12.1.1-cudnn8-conda-ubuntu20.04 -f Dockerfile  . 
```

# 创建容器

```
docker run --rm -itd --gpus all  --ipc=host --net=host --shm-size=32g --ulimit memlock=-1 --privileged -e "DISPLAY"  -v "/tmp/.X11-unix:/tmp/.X11-unix:rw" --name torchnet summit4you/cuda-12.1.1-cudnn8-conda-ubuntu20.04 bash

```

# 进入容器

```
docker exec -it torchnet bash
```

# 下载pytorch环境

```
mamba env create -f environment.yaml
```

# 激活环境

```
mamba activate torchnet
```

# 执行测试

```
git clone https://github.com/summit4you/torchnet.git
cd torchnet
python3 test_mnist.py
```
