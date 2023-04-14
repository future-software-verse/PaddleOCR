# 1、 构建移动端模型镜像

docker build -t paddleocr:cpu .

# 2、启动移动端模型镜像生成容器、注意宿主机8868端口是否已经占用

docker run -dp 8869:8866 --name paddle_ocr paddleocr:cpu

# 查看容器日志（成功运行将显示项目对应运行地址和端口）

docker logs -f paddle_ocr

## 可以尝试在根目录(父级目录)去build 镜像

docker build -t paddleocr:cpu .

docker build -t paddleocr:cpu -f  deploy/docker/hubserving/cpu/Dockerfile .
