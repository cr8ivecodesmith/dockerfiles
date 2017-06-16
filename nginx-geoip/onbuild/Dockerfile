FROM cr8ivecodesmith/nginx-geoip
MAINTAINER matt lebrun <matt@lebrun.org>

ONBUILD ADD ./*.txt /tmp/
ONBUILD RUN cd /tmp; \
    [ -f packages.txt -o -f dependencies.txt ] && apt-get update; \
    [ -f packages.txt ] && xargs -r apt-get install -y < packages.txt; \
    [ -f dependencies.txt ] && xargs -r apt-get install -y < dependencies.txt; \
    [ -f requirements.txt ] && pip install -r requirements.txt; \
    [ -f dependencies.txt ] && xargs -r apt-get purge -y --auto-remove < dependencies.txt; \
    [ -f packages.txt -o -f dependencies.txt ] && rm -rf /var/lib/apt/lists/*; \
    rm -rf /tmp/*.txt
