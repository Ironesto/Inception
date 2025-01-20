FROM debian:11

# Instalar paquetes y configurar MariaDB
RUN apt update -y && apt upgrade -y && \
    apt install -y mariadb-server && \
    mkdir -p /var/run/mysqld && \
    touch /var/run/mysqld/mysqld.sock && \
    chown mysql:mysql -R /var/run/mysqld && \
    chmod -R 755 /var/run/mysqld

COPY conf/50-server.cnf /etc/mysql/mariadb.conf.d/50-server.cnf
COPY tools/initdb.sh tools/create.sh /
RUN chmod +x /initdb.sh /create.sh
EXPOSE	3306

CMD     [ "sh", "/initdb.sh" ]