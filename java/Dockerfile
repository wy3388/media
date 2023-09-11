FROM alpine:latest

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories &&\
    apk add --no-cache ttf-dejavu fontconfig

COPY jdk.tar.gz /opt

WORKDIR /opt

RUN tar -zxvf jdk.tar.gz &&\
    mv zulu8.72.0.17-ca-jdk8.0.382-linux_musl_x64 jdk8 &&\
    rm -rf jdk.tar.gz

ENV JAVA_HOME=/opt/jdk8

ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:$JAVA_HOME/bin

ENV CLASSPATH=.:$JAVA_HOME/lib/tools.jar:$JAVA_HOME/lib/dt.jar

WORKDIR /