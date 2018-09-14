FROM ubuntu
RUN apt-get update && apt-get install mysql-server mysql-client -y
RUN find /var/lib/mysql/mysql -exec touch -c -a {} + && \ 
service mysql start && sleep 10 && echo "CREATE DATABASE abook;" | mysql -u root -ppassword && \
echo "CREATE USER 'someuser'@'%' IDENTIFIED BY 'ThisIsMyPassword';" | mysql -u root -ppassword && \
echo "GRANT ALL PRIVILEGES ON abook.* TO 'someuser'@'%' WITH GRANT OPTION; FLUSH PRIVILEGES;" | mysql -u root -ppassword && \
echo "use abook; CREATE TABLE abook (abookid INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,name VARCHAR(30) NOT NULL,address VARCHAR(30) NOT NULL) " | mysql -u root -ppassword
RUN sed -i 's/bind-address/\#bind-address/' /etc/mysql/mysql.conf.d/mysqld.cnf
EXPOSE 3306
CMD mysqld_safe



 
