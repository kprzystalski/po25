FROM ubuntu:22.04

ENV TZ=Europe/Warsaw

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y wget vim git curl

RUN apt-get install -y build-essential unzip
RUN apt-get install -y mysql-server

RUN apt-get install -y php8.1 
RUN apt-get install -y php-sqlite3 sqlite3
RUN apt-get install -y php-dom php-mysql php-xml

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | bash
RUN apt install -y symfony-cli

RUN useradd -ms /bin/bash student 
RUN adduser student sudo

EXPOSE 80
EXPOSE 45173

VOLUME /home/student/projobj/

USER student
WORKDIR /home/student/
RUN mkdir projobj
WORKDIR /home/student/projobj
CMD /bin/bash
