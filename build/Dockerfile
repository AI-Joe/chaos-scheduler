# Image building stage
FROM registry.access.redhat.com/ubi7/ubi-minimal:latest

ENV OPERATOR=/usr/local/bin/chaos-scheduler \
    USER_UID=1001 \
    USER_NAME=chaos-scheduler

# install operator binary
COPY _output/bin/chaos-scheduler ${OPERATOR}

COPY bin /usr/local/bin
RUN  /usr/local/bin/user_setup

ENTRYPOINT ["/usr/local/bin/entrypoint"]

USER ${USER_UID}
