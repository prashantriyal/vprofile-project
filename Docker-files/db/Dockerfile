FROM mysql:8.0.33
LABEL "Project"="vprofile"
LABEL "Author"="Prashant"

ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"

#it will execute sqlfile found in specified location
ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql