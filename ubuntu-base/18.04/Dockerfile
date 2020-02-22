FROM ubuntu:18.04
LABEL maintainer="lephix@163.com"
LABEL description="This is a Ubuntu:18:04 base image. We love Ubuntu right?"

# set locales
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
ENV LANG en_US.utf8

# set timezone
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install tzdata
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN dpkg-reconfigure --frontend noninteractive tzdata

# add tools
RUN apt-get update && apt-get install -y curl wget vim python3 \
	&& apt-get purge -y
