FROM ubuntu:20.04
ENV TZ=Asia/Kolkata
ENV DEBIAN_FRONTEND=noninteractive

RUN apt update && apt upgrade -y
RUN apt install htop apache2 php libapache2-mod-php php-mysql git nano -y
RUN apt install -y locales locales-all
RUN locale-gen --purge en_US.UTF-8

WORKDIR /var/www/html
COPY /source-code/. /var/www/html/
COPY /scripts/. /var/scripts/

RUN chmod +x /var/scripts/entry.sh

EXPOSE 80

CMD /var/scripts/entry.sh