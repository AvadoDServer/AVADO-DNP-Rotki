ARG VERSION=latest
FROM rotki/rotki:${VERSION}

# Set up nginx config
COPY ssl.conf /etc/nginx/conf.d/ssl.conf

RUN mkdir -p /etc/nginx/certs/
ADD "https://www.random.org/cgi-bin/randbyte?nbytes=10&format=h" skipcache
RUN curl http://iso.ava.do/my.ava.do.crt --output /etc/nginx/certs/my.ava.do.crt
RUN curl http://iso.ava.do/my.ava.do.key --output /etc/nginx/certs/my.ava.do.key
RUN ls -l /etc/nginx/certs/