FROM advancedclimatesystems/python:3.4.3
MAINTAINER Auke Willem Oosterhoff <auke@orangetux.nl>

COPY wheelhouse /wheelhouse

RUN pip install --find-links wheelhouse \
    flask \
    flask-redis \
    uwsgi
RUN pip install --upgrade pip

COPY src /app
COPY uwsgi.ini /etc/uwsgi.ini
COPY shared_libs/* /lib/

CMD uwsgi --ini /etc/uwsgi.ini
