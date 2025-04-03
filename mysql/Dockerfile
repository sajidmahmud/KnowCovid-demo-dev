FROM mysql:latest

MAINTAINER Songjie Wang "wangso@missouri.edu"

ARG DEBIAN_FRONTEND=noninteractive
ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_USER=covid19-user
ENV MYSQL_PASSWORD=covid19-pass
ENV MYSQL_DATABASE=covid19

# Copy your custom entrypoint script into the container
COPY entrypoint.sh /entrypoint.sh

# Ensure the script is executable
RUN chmod +x /entrypoint.sh

# Copy the SQL script to initialize the DB
COPY covid19.sql /docker-entrypoint-initdb.d/

# Set your custom entrypoint
ENTRYPOINT ["/entrypoint.sh"]

# Start MySQL server
CMD ["mysqld"]
