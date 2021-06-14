FROM alpine:latest
RUN apk add --no-cache curl ca-certificates

# add fivem repositories
RUN curl --http1.1 -sLo /etc/apk/keys/peachypies@protonmail.ch-5adb3818.rsa.pub https://runtime.fivem.net/client/alpine/peachypies@protonmail.ch-5adb3818.rsa.pub

RUN echo https://runtime.fivem.net/client/alpine/builds >> /etc/apk/repositories
RUN echo https://runtime.fivem.net/client/alpine/main >> /etc/apk/repositories
RUN echo https://runtime.fivem.net/client/alpine/testing >> /etc/apk/repositories
RUN echo https://runtime.fivem.net/client/alpine/community >> /etc/apk/repositories
RUN apk --no-cache update

RUN apk add --no-cache curl=7.63.0-r99 libssl1.1 libunwind libstdc++ zlib c-ares icu-libs v8 musl-dbg execline
RUN curl https://runtime.fivem.net/artifacts/fivem/build_proot_linux/master/3922-d59ca5ee4232a9d636fd71e116f61960e974b29e/fx.tar.xz | tar xJ -C /srv

WORKDIR /srv

EXPOSE 30120/tcp 30120/udp 40120/tcp

ENTRYPOINT ["sh", "/srv/run.sh"]