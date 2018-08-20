FROM python:3.6.6-jessie

RUN mkdir -p /data/web
RUN cd /data/web
WORKDIR /data/web
COPY ./Pipfile ./Pipfile.lock /data/web/

RUN apt-get -y update
RUN apt-get -y upgrade
RUN apt-get -y install postgresql-client python3-dev libpq-dev gettext libsasl2-dev libldap2-dev libssl-dev
RUN pip3 install --upgrade pip
RUN pip3 install pipenv
RUN pipenv install --system

COPY . /data/web

# RUN python3 manage.py collectstatic

EXPOSE 8000
