FROM ubuntu
WORKDIR /code
RUN sed -i s@/archive.ubuntu.com/@/mirrors.aliyun.com/@g /etc/apt/sources.list
RUN apt clean
RUN apt update -y
RUN apt install -y python3 python3-pip
RUN pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple fastapi uvicorn
RUN pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple nameko
ENV nameko_username=rabbitmq_admin nameko_password=Cisc0123 rabbitmq_host=rabbitmq
EXPOSE 8089
COPY . .
CMD ["python3", "server.py"]