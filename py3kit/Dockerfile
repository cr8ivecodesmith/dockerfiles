FROM python:3.5
ENV DEBIAN_FRONTEND noninteractive
MAINTAINER matt lebrun <matt@lebrun.org>

ADD requirements.txt /opt/
WORKDIR /opt/
RUN useradd cr8ivecodesmith \
    && pip install -r requirements.txt

RUN apt-get autoclean -y \
    && apt-get autoremove -y \
    && apt-get purge -y \
    && rm /opt/requirements.txt

USER cr8ivecodesmith
CMD ["ipython"]
