FROM ubuntu:latest

RUN apt update && apt install  openssh-server sudo -y

# Permit root login and change root password
RUN echo "root:root" | chpasswd && \
    sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# Crea y cambia contraseña usuario test
RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1000 test 
RUN  echo 'test:test' | chpasswd

# SSH login fix. Otherwise user is kicked off after login
RUN mkdir /var/run/sshd


# RUN service ssh start
EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]