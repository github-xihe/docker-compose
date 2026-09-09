# 制作 OpenJDK 21 JRE 镜像

基于 Eclipse Temurin 21 和 Ubuntu Noble，默认使用 `Asia/Shanghai` 时区。

基础镜像已包含 `tzdata`，无需重复安装。

```shell
# 构建并推送 amd64、arm64 多架构镜像  注：有点慢
docker buildx build \
  --platform linux/amd64,linux/arm64 \
  -t registry.cn-hangzhou.aliyuncs.com/zhengqing/openjdk:21 \
  . --no-cache --push

# Dockerfile中引用新镜像
# FROM registry.cn-hangzhou.aliyuncs.com/zhengqing/openjdk:21
```
