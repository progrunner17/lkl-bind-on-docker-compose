FROM alpine:3.9

RUN apk update \
        && apk add bind \
        && apk add bind-tools \
        && apk add bind-dnssec-tools \
        && rm -rf /var/cache/apk/* \
        && chown -R named:named /var/bind \
        && chmod -R u+rwx /var/bind

EXPOSE 53

CMD ["/usr/sbin/named", "-g", "-u", "named", "-c", "/etc/bind/named.conf"]
