FROM ubuntu:20.04

WORKDIR /usr/src/app

RUN apt-get update \
  && apt-get install -y curl

COPY file1.bash .

RUN chmod +x file1.bash

CMD ./file1.bash