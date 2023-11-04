# Use an official MariaDB image as the base image
FROM mariadb:11.1.2

# Set the default authentication plugin for MariaDB
CMD ["--default-authentication-plugin=mysql_native_password"]

# Expose the MySQL port (3306)
EXPOSE 3306

# Copy your custom MariaDB configuration file to the container
# COPY my-mariadb.cnf /etc/mysql/my.cnf

# Set environment variables for database name and root password
ENV MYSQL_DATABASE=sms_test
ENV MYSQL_ROOT_PASSWORD=myrootpassword

# Create a volume for data persistence
VOLUME /var/lib/mysql

# Healthcheck configuration
HEALTHCHECK --interval=3s --retries=5 --start-period=30s \
  CMD mysqladmin ping -h 127.0.0.1 --password="$MYSQL_ROOT_PASSWORD" --silent
