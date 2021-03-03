FROM mysql:latest

LABEL maintainer=yuartian(https://github.com/YuArtian)

ENV MYSQL_ROOT_PASSWORD=123456

COPY init.sql /docker-entrypoint-initdb.d
