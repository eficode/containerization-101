FROM        ubuntu:14.04
MAINTAINER  Markus Suonto

RUN         apt-get update
RUN         apt-get install -y python

ADD         demoapp /opt/demoapp
RUN         chmod 744 /opt/demoapp/server.py

EXPOSE      7272

ENTRYPOINT  ["/opt/demoapp/server.py"]
