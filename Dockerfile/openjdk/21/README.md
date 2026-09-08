# 制作 OpenJDK 21 JRE 镜像

基于 Eclipse Temurin 21 和 Ubuntu Noble，默认使用 `Asia/Shanghai` 时区。

基础镜像已包含 `tzdata`，无需重复安装。

```shell
# 构建镜像 注：有点慢
docker build -t registry.cn-hangzhou.aliyuncs.com/zhengqing/openjdk:21 . --no-cache

# 推送镜像
docker push registry.cn-hangzhou.aliyuncs.com/zhengqing/openjdk:21

# Dockerfile中引用新镜像
# FROM registry.cn-hangzhou.aliyuncs.com/zhengqing/openjdk:21
```
