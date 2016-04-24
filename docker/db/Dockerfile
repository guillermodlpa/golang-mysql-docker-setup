FROM mysql:5.7

MAINTAINER Guillermo de la Puente <g.puente.allott@gmail.com>

VOLUME ["/var/lib/mysql"]

RUN sed -i "s/^user.*/user = root/g" /etc/mysql/my.cnf

RUN chown -R mysql /var/lib/mysql
RUN chgrp -R mysql /var/lib/mysql