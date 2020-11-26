FROM alpine:3.11
RUN apk --no-cache add make gcc musl-dev libffi-dev openssl-dev python3-dev python3
#RUN python3 -m pip install azure-cli-core azure-cli-acs azure-cli-acr
RUN python3 -m pip install ansible[azure]==2.9.10 ansible-lint six molecule python-vagrant openshift
RUN apk --no-cache del make gcc musl-dev libffi-dev openssl-dev python3-dev
ENV HOME=/ansible
RUN mkdir /ansible
WORKDIR /ansible
