FROM centos:7

RUN set -x && \
    yum update -y && \
    yum install -y sudo curl gcc-c++ make && \
    yum reinstall -y glibc-common && \
    yum -y clean all

# install nodejs
RUN set -x && \
    curl -sL https://rpm.nodesource.com/setup_10.x | bash - && \
    yum install -y nodejs && \
    yum -y clean all

# install git
RUN set -x && \
    yum install -y git && \
    yum -y clean all

# locale settings
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja

RUN localedef -i ja_JP -c -f UTF-8 ja_JP.UTF-8 && \
    unlink /etc/localtime && \
    ln -s /usr/share/zoneinfo/Japan /etc/localtime

# application user settings
ENV HOME /home/app

RUN set -x && \
    groupadd app && \
    useradd -g app -d /home/app -s /bin/bash app

# add sudo group
RUN echo 'app:app' | chpasswd && \
    echo 'app ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

WORKDIR $HOME
USER app

COPY test.txt .

# ENTRYPOINT [ "/bin/bash" ]
