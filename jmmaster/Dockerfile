FROM adoptopenjdk/openjdk8:aarch64-ubuntu-jre8u322-b06

LABEL org.opencontainers.image.authors="DimCyan"

ARG JMETER_VERSION=5.4.3

RUN apt-get clean && \
    apt-get update && \
    apt-get -qy install \
                wget \
                telnet \
                iputils-ping

RUN mkdir /jmeter
WORKDIR /jmeter
RUN curl https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-${JMETER_VERSION}.tgz --output jmeter.tgz \
    && tar -xzf jmeter.tgz -C /jmeter

ENV JMETER_HOME=/jmeter/apache-jmeter-${JMETER_VERSION}
ENV JMETER_PATH=${JMETER_HOME}/bin:${PATH}
ENV PATH=${JMETER_HOME}/bin:${PATH}

WORKDIR /jmeter/apache-jmeter-${JMETER_VERSION}/bin

EXPOSE 60000