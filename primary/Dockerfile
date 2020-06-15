FROM alpine:3.9 as data-src

RUN apk update \
        && apk add bind \
        && apk add bind-tools \
        && apk add bind-dnssec-tools \
        && rm -rf /var/cache/apk/* \
        && chown -R named:named /var/bind \
        && chmod -R u+rwx /var/bind

FROM thehajime/runu-named:0.3

COPY --from=data-src /var /var
ADD ./etc/bind  /etc/bind
ADD ./var/bind/* /var/bind/

CMD ["named", "-c", "/etc/bind/named.conf", "-g"]

