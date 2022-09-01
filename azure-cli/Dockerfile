FROM alpine:3.16
RUN apk --no-cache add make gcc musl-dev libffi-dev openssl-dev python3-dev python3 py3-pip
#RUN python3 -m pip install azure-cli-core azure-cli-acs azure-cli-acr
RUN python3 -m pip install azure-cli
RUN apk --no-cache del make gcc musl-dev libffi-dev openssl-dev python3-dev
ENV HOME=/azure
RUN mkdir /azure
WORKDIR /azure
