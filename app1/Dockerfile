FROM ubuntu:18.04

RUN set -x && \
    apt-get update && \
    apt-get install -y locales tzdata && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get clean all

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

WORKDIR $HOME
USER app

COPY test.txt .

# ENTRYPOINT [ "/bin/bash" ]
