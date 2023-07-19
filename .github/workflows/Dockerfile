FROM ubuntu:22.04
LABEL autor=Shadowcross
RUN apt-get update && apt-get upgrade
RUN apt-get install nginx -y
RUN mkdir -p /var/run/sshd
RUN apt update && \
    apt install -y openssh-server
RUN useradd -rm -d /home/remote_user -s /bin/bash remote_user && \
    echo remote_user:password1234 | chpasswd
RUN mkdir /root/.ssh/
RUN cd /root/.ssh/
RUN touch config

COPY index.html /var/www/html/
 
ENV OWNER=Dima
ENV TYPE=full

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
