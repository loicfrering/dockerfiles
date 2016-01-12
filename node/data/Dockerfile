FROM busybox
MAINTAINER Loïc Frering <loic.frering@gmail.com>

RUN mkdir /nodedata
RUN mkdir /nodedata/npm-cache
RUN chmod -R 777 /nodedata

VOLUME /nodedata
WORKDIR /nodedata
CMD /bin/true
