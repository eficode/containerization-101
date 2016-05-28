FROM        ubuntu:14.04
MAINTAINER  Markus Suonto

RUN         apt-get update
RUN         apt-get install -y xvfb firefox

RUN         curl --silent --show-error --retry 5 https://bootstrap.pypa.io/get-pip.py | python2.7
RUN         pip install robotframework robotframework-selenium2library xvfbwrapper robotframework-xvfb

ADD         robo-tests /opt/robo-tests

# Needs to mount /opt/robo-tests/output
ENTRYPOINT  ["pybot /opt/robo-tests --outputdir"]
