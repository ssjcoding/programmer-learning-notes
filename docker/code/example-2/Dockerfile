## 相关Dockerfile文件内容如下

# 使用官方提供的 Python 作为我们镜像的基础环境
FROM daocloud.io/library/python:3.5-slim

# 将工作目录切换为 /Users/ssh/Documents/private/project/github/programmer-learning-notes/docker/code/example-2/test
WORKDIR /Users/ssh/Documents/private/project/github/programmer-learning-notes/docker/code/example-2/test

# 将当前目录下的所有内容复制到 /Users/ssh/Documents/private/project/github/programmer-learning-notes/docker/code/example-2/test 下
ADD . /Users/ssh/Documents/private/project/github/programmer-learning-notes/docker/code/example-2/test

# 使用 pip 命令安装这个应用所需要的依赖
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# 允许外界访问容器的 80 端口
EXPOSE 80

# 设置环境变量
ENV NAME World

# 设置容器进程为：python app.py，即：这个 Python 应用的启动命令
CMD ["python", "app.py"]
