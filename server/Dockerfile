FROM ubuntu:latest
ENV LANG=C.UTF-8 LC_ALL=C.UTF-8

RUN apt-get update \
  && apt-get install -y gnupg2 curl apt-transport-https build-essential \
  && curl -s https://packages.microsoft.com/config/debian/9/prod.list > /etc/apt/sources.list.d/mssql-release.list \
  && curl -s https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && apt-get update \
  && ACCEPT_EULA=Y apt-get install -y ca-certificates libkrb5-3 libpq5 libnuma1 unixodbc-dev msodbcsql17 default-libmysqlclient-dev default-mysql-client \
  && apt-get -y remove curl gnupg2 \
  && apt-get -y auto-remove \
  && apt-get -y clean \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /usr/share/doc/ \
  && rm -rf /usr/share/man/ \
  && rm -rf /usr/share/locale/

CMD ["/bin/sh"]