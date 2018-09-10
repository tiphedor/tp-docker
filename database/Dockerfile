FROM postgres:9.6-alpine

ENV POSTGRES_PASSWORD ""
ENV POSTGRES_USER gordonuser
ENV POSTGRES_DB ddev

COPY ./pg_hba.conf /usr/share/postgresql/9.6/
COPY ./postgresql.conf /usr/share/postgresql/9.6/

COPY ./init-db.sql /docker-entrypoint-initdb.d
