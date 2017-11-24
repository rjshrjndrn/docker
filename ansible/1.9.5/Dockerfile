FROM alpine:3.5
RUN apk --update --no-cache add build-base libffi-dev openssl-dev python-dev py-pip \
 && pip install cffi && pip install ansible==1.9.5 \
 && apk del build-base py-pip &&rm -rf /root/cache \
 && mkdir /ansible
VOLUME /ansible
WORKDIR /ansible
CMD ["/usr/bin/ansible", "--version"]
