FROM registry.access.redhat.com/ubi7-dev-preview/ubi-minimal:7.6

ENV OPERATOR=/usr/local/bin/chaos-operator \
    USER_UID=1001 \
    USER_NAME=chaos-operator

ARG BUILD_DATE
LABEL org.label-schema.name="chaos-operator"
LABEL org.label-schema.description="Kubernetes Operator for LitmusChaos"
LABEL org.label-schema.url="http://www.litmuschaos.io/"
LABEL org.label-schema.vcs-url="https://github.com/litmuschaos/chaos-operator"
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE

# install operator binary
COPY bin/chaos-operator/chaos-operator ${OPERATOR}
#build/_output/bin/chaos-operator

COPY build/bin /usr/local/bin
RUN  /usr/local/bin/user_setup

ENTRYPOINT ["/usr/local/bin/entrypoint"]

USER ${USER_UID}
