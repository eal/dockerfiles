# create an image that is suitable as a builder image for substratevm binaries
FROM ubuntu:bionic
RUN apt-get update
RUN apt-get install -yy curl leiningen build-essential zlib1g-dev upx
RUN cd /opt && curl -sL https://github.com/oracle/graal/releases/download/vm-1.0.0-rc6/graalvm-ce-1.0.0-rc6-linux-amd64.tar.gz | tar -xzvf -
RUN ln -s /opt/graalvm-ce-1.0.0-rc6 /opt/graalvm

