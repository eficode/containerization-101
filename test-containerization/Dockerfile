FROM        ubuntu:14.04
MAINTAINER  Markus Suonto

RUN         apt-get update
RUN         apt-get install -y python curl
RUN         apt-get install -y xvfb firefox

RUN         curl --silent --show-error --retry 5 https://bootstrap.pypa.io/get-pip.py | python2.7
RUN         pip install robotframework robotframework-selenium2library xvfbwrapper robotframework-xvfb

RUN         mkdir -p /robo-tests/output

ENTRYPOINT  ["pybot"]
