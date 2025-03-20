FROM ubuntu:22.04

ENV TZ=Europe/Warsaw


RUN apt-get update && apt-get install -y wget vim git curl

RUN apt-get install -y build-essential unzip

RUN apt-get install -y fp-compiler

RUN useradd -ms /bin/bash student 
RUN adduser student sudo


EXPOSE 80

VOLUME /home/student/skrypty/

USER student
WORKDIR /home/student/
RUN mkdir projobj
WORKDIR /home/student/projobj
CMD /bin/bash
