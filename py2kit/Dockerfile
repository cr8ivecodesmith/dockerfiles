FROM python:2.7
MAINTAINER matt lebrun <matt@lebrun.org>

RUN mkdir /_build/
ADD requirements.txt /_build/
WORKDIR /_build/
RUN useradd -U -M -s /bin/bash pykit \
    && pip install -r requirements.txt

RUN apt-get autoclean -y \
    && apt-get autoremove -y \
    && apt-get purge -y \
    && rm -rf /_build/

USER pykit
CMD ["python"]
