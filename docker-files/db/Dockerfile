# Reference: https://hub.docker.com/_/mysql
# We use MySQL 8.0 to match what vProfile expects.
FROM mysql:8.0


# These environment variables are documented on the Docker Hub page.
# MYSQL_ROOT_PASSWORD: Required. MySQL will not start without it.
# MYSQL_DATABASE: Creates this database automatically on first boot.
# MYSQL_USER + MYSQL_PASSWORD: Creates a non-root user with full
#   privileges on MYSQL_DATABASE. This matches what application.properties
#   expects: username=admin, password=admin123
ENV MYSQL_ROOT_PASSWORD="admin123"
ENV MYSQL_DATABASE="accounts"
ENV MYSQL_USER="admin"
ENV MYSQL_PASSWORD="admin123"


# The Docker Hub documentation states that any .sql file placed in
# /docker-entrypoint-initdb.d/ is executed on first container startup.
# This is the official way to seed a MySQL container with data.
# We are not inventing this path — it is built into the image.
COPY db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql


# MySQL listens on port 3306 by default (documented on Docker Hub).
EXPOSE 3306
