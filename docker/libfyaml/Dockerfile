ARG FROM
FROM $FROM
ARG REPO
ARG TAG

RUN git clone --branch=$TAG $REPO /build

WORKDIR /build

RUN ./bootstrap.sh \
 && ./configure \
 && make install

COPY bin/* /export/usr/local/bin/

RUN cp -P \
        /usr/local/bin/fy-tool \
        /export/usr/local/bin/ \
 && cp -P \
        /usr/local/lib/libfyaml* \
        /export/usr/local/lib/ \
 && true
