FROM alpine:3.11.5
RUN apk add --no-cache openssl nmap nmap-nping nmap-ncat nmap-scripts heimdal netcat-openbsd tcpdump ca-certificates curl bash bind-tools jq w3m openssh-client
RUN curl -L -o /tmp/kaf.tgz https://github.com/birdayz/kaf/releases/download/v0.1.33/kaf_0.1.33_Linux_x86_64.tar.gz && cd /tmp; tar xzf /tmp/kaf.tgz && cp /tmp/kaf /usr/local/bin && chmod 755 /usr/local/bin/kaf; mkdir -p /root/.kaf
# CMD ["tail", "-f", "/dev/null"]
