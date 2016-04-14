FROM alpine:3.3
RUN apk --no-cache add dnsmasq
# RUN wget -O /etc/hosts https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts
 RUN mkdir /etc/badhosts
ADD ./download/* /etc/badhosts/
RUN chmod 444 /etc/badhosts/*
EXPOSE 53 53/udp

CMD ["dnsmasq", "-k", "-b", "-B", "0.0.0.0", "-H", "/etc/badhosts/", "--cache-size=10000"]
