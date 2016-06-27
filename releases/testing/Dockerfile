FROM coldrye/debian-jetty:9-3-9-testing-latest

MAINTAINER Carsten Klein <trancesilken@gmail.com>

ARG FEATURE_VERSION=
ARG STORAGE_DIR=
ARG DEPLOY_DIR=

RUN test -z "$FEATURE_VERSION" && echo "FEATURE_VERSION missing" && exit 1 || true
RUN test -z "$STORAGE_DIR" && echo "STORAGE_DIR missing" && exit 1 || true
RUN test -z "$DEPLOY_DIR" && echo "DEPLOY_DIR missing" && exit 1 || true

VOLUME $STORAGE_DIR

RUN set -x \
    && curl -fSL https://updates.jenkins-ci.org/download/war/$FEATURE_VERSION/jenkins.war -o $DEPLOY_DIR/webapps/jenkins.war \
    && mkdir -p $STORAGE_DIR

ADD ["etc/default/jetty", "/etc/default/"]
ADD ["conf/jenkins.xml", "$DEPLOY_DIR/webapps/"]

