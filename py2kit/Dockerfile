FROM python:2.7
MAINTAINER matt lebrun <matt@lebrun.org>

ADD requirements.txt /
RUN  pip install -r requirements.txt

RUN apt-get autoclean -y \
    && apt-get autoremove -y \
    && apt-get purge -y \
    && rm -rf /requirements.txt

CMD ["python"]
