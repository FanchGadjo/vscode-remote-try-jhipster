FROM ubuntu:bionic

# Configure apt
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update \
    && apt-get -y install --no-install-recommends apt-utils \
    wget \
    curl \
    vim \
    git \
    zip \
    bzip2 \
    fontconfig \
    python \
    g++ \
    libpng-dev \
    build-essential \
    software-properties-common \
    procps \
    lsb-release \
    ca-certificates \
    gnupg-agent \
    sudo && \
  # install OpenJDK 11
  add-apt-repository ppa:openjdk-r/ppa && \
  apt-get update && \
  apt-get install -y openjdk-11-jdk && \
  update-java-alternatives -s java-1.11.0-openjdk-amd64 && \
  # install node.js
  wget https://nodejs.org/dist/v10.15.3/node-v10.15.3-linux-x64.tar.gz -O /tmp/node.tar.gz && \
  tar -C /usr/local --strip-components 1 -xzf /tmp/node.tar.gz && \
  # upgrade npm
  npm install -g npm

# Docker in Docker setup https://github.com/Microsoft/vscode-dev-containers/tree/63cc8842ea3553db09e8207032202557ca9be3d7/containers/docker-in-docker
RUN curl -fsSL https://download.docker.com/linux/$(lsb_release -is | tr '[:upper:]' '[:lower:]')/gpg | apt-key add - 2>/dev/null \
    && add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/$(lsb_release -is | tr '[:upper:]' '[:lower:]') $(lsb_release -cs) stable" \
    && apt-get update \
    && apt-get install -y docker-ce-cli \
    && curl -L https://github.com/docker/compose/releases/download/1.24.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose \
    && chmod +x /usr/local/bin/docker-compose \
    && rm get-docker.sh

COPY settings.vscode.json /root/.vscode-remote/data/Machine/settings.json

RUN npm install -g generator-jhipster

# Clean up
RUN apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*
ENV DEBIAN_FRONTEND=dialog

EXPOSE 8080 9000 3001
