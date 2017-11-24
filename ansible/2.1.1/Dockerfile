FROM alpine:3.5
# making an addtional layer as ssh and python are necessory
# so caching will be efficient
RUN apk --update --no-cache add openssh python-dev
RUN apk --update --no-cache add build-base libffi-dev openssl-dev py-pip \
 && pip install cffi && pip install ansible==2.1.1 \
 && pip uninstall -y cffi \
 && apk del build-base py-pip libffi-dev openssl-dev &&rm -rf /root/cache \
 && mkdir /ansible
ENV SSH_AUTH_SOCK=/ssh-agent
VOLUME /ssh-agent
VOLUME /ansible
WORKDIR /ansible
CMD ["/usr/bin/ansible", "--version"]
