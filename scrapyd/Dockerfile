FROM ubuntu:trusty
ENV DEBIAN_FRONTEND noninteractive
MAINTAINER matt lebrun <lebrun.matt@gmail.com>

RUN apt-get update && apt-get install -y \
    build-essential \
    curl \
    git \
    libffi-dev \
    libssl-dev \
    libxml2-dev \
    libxslt1-dev \
    libtool \
    python \
    python-dev \
    python-setuptools \
    vim-tiny

RUN easy_install -U pip

RUN pip install \
    git+https://github.com/scrapy/scrapy.git \
    git+https://github.com/scrapy/scrapyd.git \
    git+https://github.com/scrapy/scrapyd-client.git

ADD ./scrapyd.conf /etc/scrapyd/
VOLUME /etc/scrapyd/ /var/lib/scrapyd/
EXPOSE 6800

CMD ['scrapyd']
