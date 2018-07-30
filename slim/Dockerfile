FROM debian:sid-slim
LABEL maintainer="Filipe Regadas <filiperegadas@gmail.com>"

ENV LANG C.UTF-8

RUN apt-get update && apt-get install -y --no-install-recommends \
        bzip2 \
        unzip \
        xz-utils \
        curl

ARG GRAAL_VERSION

RUN apt-get install -y --no-install-recommends ca-certificates && \
    curl -fsSL "https://github.com/oracle/graal/releases/download/vm-${GRAAL_VERSION}/graalvm-ce-${GRAAL_VERSION}-linux-amd64.tar.gz" | tar -xz && \
    rm -r /var/lib/apt/lists/*

ENV JAVA_HOME /graalvm-ce-${GRAAL_VERSION}
ENV GRAAL_HOME /graalvm-ce-${GRAAL_VERSION}

ENV PATH $PATH:$GRAAL_HOME/jre/bin:$GRAAL_HOME/bin

