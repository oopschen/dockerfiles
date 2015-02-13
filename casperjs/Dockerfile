# docker container for casperjs using phatomjs
# @version
#   phantomjs: 1.9.8
#   casperjs: 1.1.0-beta3
#
# @Usage
# docker run --entrypoint="/usr/bin/phantomjs" oopschen/phantomjs -v 
# docker run -v `pwd`:/mnt oopschen/phantomjs scriptfile
FROM python:2.7.9

MAINTAINER oopschen

# Env
ENV INSTALLDIR /opt
RUN mkdir -p $INSTALLDIR

# Add source file
COPY src $INSTALLDIR

# Commands
RUN \
  ln -s $INSTALLDIR/phantomjs/bin/phantomjs /usr/bin/phantomjs && \
  ln -sf $INSTALLDIR/casperjs/bin/casperjs /usr/bin/casperjs

# Default command
ENTRYPOINT ["/usr/bin/casperjs", "--engine=phantomjs"]
CMD ["--version"]
