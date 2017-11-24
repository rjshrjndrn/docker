FROM alpine:3.5
RUN apk --update --no-cache add openssh build-base libffi-dev openssl-dev python-dev py-pip \
 && pip install cffi && pip install ansible==2.1.1 \
 && pip uninstall -y cffi \
 && apk del build-base py-pip libffi-dev openssl-dev &&rm -rf /root/cache \
 && mkdir /ansible
ENV SSH_AUTH_SOCK=/ssh-agent
VOLUME /ssh-agent
VOLUME /ansible
WORKDIR /ansible
CMD ["/usr/bin/ansible", "--version"]
