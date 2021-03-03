# docker-mysql-init
Docker初始化MySQL示例

### 需求

在 Docker 创建 MySQL 容器之后，希望能自动创建项目需要的库和表，初始数据也需要自动录入。要做到 MySQL 的容器启动好之后，数据库就是可用的状态。

所以，需要容器启动时可以执行 sql 脚本

### 实现原理

在 MySQL 官方镜像中提供了容器启动时自动执行 `docker-entrypoint-initdb.d` 文件夹下脚本的功能

所以简单来讲，只需要将 sql 脚本放入  `docker-entrypoint-initdb.d` 文件夹下就行了

但是，如果有多个 sql 需要依次执行，就要依赖 sh 进行控制

具体可查看 `simple` 和 `multiple` 文件夹下的示例

### 使用
#### 简单
`docker build -t mysql_simple_init .`
`docker run -p 3306:3306 --name mysql_simple -d mysql_simple_init --max_connections=1000 --character-set-server=utf8mb4 --collation-server=utf8mb4_general_ci --default-authentication-plugin=mysql_native_password`

#### 多个sql顺序执行
`docker build -t mysql_multiple_init .`
`docker run -p 3306:3306 --name mysql_multiple -d mysql_multiple_init --max_connections=1000 --character-set-server=utf8mb4 --collation-server=utf8mb4_general_ci --default-authentication-plugin=mysql_native_password`