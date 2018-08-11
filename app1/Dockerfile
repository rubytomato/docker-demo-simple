FROM ubuntu:18.04

RUN set -x && \
    apt update && \
    apt install -y sudo locales tzdata apt-utils curl gcc g++ make gnupg2 && \
    apt clean

# install nodejs
RUN set -x && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash - && \
    apt install -y nodejs && \
    apt clean

# install git
RUN set -x && \
    apt install -y git && \
    apt clean

# locale settings
RUN localedef -i ja_JP -c -f UTF-8 -A /usr/share/locale/locale.alias ja_JP.UTF-8 && \
    unlink /etc/localtime && \
    ln -s /usr/share/zoneinfo/Japan /etc/localtime

ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja

# application user settings
ENV HOME /home/app

RUN set -x && \
    adduser --disabled-password --gecos "" --home /home/app --shell /bin/bash app

# add sudo group
RUN echo 'app:app' | chpasswd && \
    echo 'app ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

WORKDIR $HOME
USER app

COPY test.txt .

# ENTRYPOINT [ "/bin/bash" ]
