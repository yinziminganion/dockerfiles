FROM ubuntu:16.04
MAINTAINER yinziming <i@yinziming.com>

RUN sed -i 's/archive.ubuntu.com/mirrors.bfsu.edu.cn/g' /etc/apt/sources.list
RUN sed -i 's/security.ubuntu.com/mirrors.bfsu.edu.cn/g' /etc/apt/sources.list
RUN apt update
RUN apt install -y wget
RUN apt install -y openssh-server
RUN useradd ubuntu -m -gsudo

USER ubuntu
WORKDIR /home/ubuntu

RUN wget https://mirrors.bfsu.edu.cn/anaconda/archive/Anaconda3-2020.11-Linux-x86_64.sh
RUN bash Anaconda3-2020.11-Linux-x86_64.sh -b
RUN /home/ubuntu/anaconda3/condabin/conda init
RUN rm -f Anaconda3-2020.11-Linux-x86_64.sh
COPY .condarc /home/ubuntu/.condarc

ENTRYPOINT ["bash"]
