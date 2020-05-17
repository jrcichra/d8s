FROM debian:10
### GETTING SSH IN THE CONTAINER - DO NOT MODIFY
RUN apt-get update
RUN apt-get install -y openssh-server && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN mkdir /var/run/sshd && \
    echo 'root:root' |chpasswd && \
    sed -ri 's/^#?PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config && \
    mkdir /root/.ssh
EXPOSE 22
### INSTALL EXTRA PROGRAMS YOU WANT HERE
RUN apt-get update && apt-get install -y vim openssh-server htop && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
