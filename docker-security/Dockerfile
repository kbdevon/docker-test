FROM ubuntu:trusty

USER root

ENV PASS="SUPER_SECURE_PASSWORD"

RUN apt-get update && \
    apt-get install -y wget nano curl make ssh libcap2-bin libcap-ng-utils

RUN useradd -ms /bin/bash dockersecurity

RUN echo "${PASS}" > /password.txt

RUN rm /password.txt

COPY . /mount

EXPOSE 22

USER dockersecurity

WORKDIR /tmp

CMD ["tail", "-f", "/dev/null"]
