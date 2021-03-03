# docker-mysql-init
Docker初始化MySQL示例

简单
docker build -t mysql_simple_init .
docker run -p 3306:3306 --name mysql_simple -d mysql_simple_init --max_connections=1000 --character-set-server=utf8mb4 --collation-server=utf8mb4_general_ci --default-authentication-plugin=mysql_native_password

多个sql顺序执行
docker build -t mysql_multiple_init .
docker run -p 3306:3306 --name mysql_multiple -d mysql_multiple_init --max_connections=1000 --character-set-server=utf8mb4 --collation-server=utf8mb4_general_ci --default-authentication-plugin=mysql_native_password