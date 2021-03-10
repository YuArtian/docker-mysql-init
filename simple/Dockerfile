FROM mysql:latest

LABEL maintainer=yuartian(https://github.com/YuArtian)

ENV MYSQL_ROOT_PASSWORD=123456

COPY init.sql /docker-entrypoint-initdb.d

CMD [ "--max_connections=1000","--character-set-server=utf8mb4","--collation-server=utf8mb4_general_ci", "--default-authentication-plugin=mysql_native_password"]
