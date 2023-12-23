FROM centos:latest

RUN yum install -y httpd

RUN systemctl start httpd

RUN systemctl enable httpd

COPY ./index.html /var/www/html/index.html

EXPOSE 80

CMD ["usr/sbin/httpd", "-D", "FOREGROUND"]
