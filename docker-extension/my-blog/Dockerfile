# Docker image for springboot file run
# VERSION 0.0.1
# Author: pibigstar
# 基础镜像使用java
FROM java:8
# VOLUME 指定了临时文件目录为/tmp。
# 其效果是在主机 /var/lib/docker 目录下创建了一个临时文件，并链接到容器的/tmp
VOLUME /tmp
# 将jar包添加到容器中并更名为app.jar
ADD *.jar app.jar
COPY startup.sh /startup.sh
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
# 运行jar包
RUN bash -c 'touch /app.jar'
CMD ["sh", "/startup.sh"]
#CMD java -jar /app.jar
