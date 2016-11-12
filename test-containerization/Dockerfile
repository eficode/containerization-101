FROM        ubuntu:14.04
MAINTAINER  Markus Suonto

RUN         apt-get update
RUN         apt-get install -y python curl xvfb firefox

RUN         curl -L -O https://ftp.mozilla.org/pub/firefox/releases/45.0esr/linux-x86_64/en-US/firefox-45.0esr.tar.bz2
RUN         tar -C /opt -xjf firefox-45.0esr.tar.bz2 \
 &&         rm firefox-45.0esr.tar.bz2 \
 &&         rm -f /usr/bin/firefox \
 &&         ln -s /opt/firefox/firefox /usr/bin/firefox

RUN         curl --silent --show-error --retry 5 https://bootstrap.pypa.io/get-pip.py | python2.7
RUN         pip install robotframework selenium==2.53.6 robotframework-selenium2library xvfbwrapper robotframework-xvfb

RUN         mkdir -p /robo-tests/output

ENTRYPOINT  ["pybot"]
