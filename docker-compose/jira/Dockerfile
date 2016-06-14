FROM ubuntu:trusty

RUN apt-get update -y && apt-get install -y unzip curl

ADD response.varfile /tmp/response.varfile

RUN mkdir -p /tmp/jira \
 && curl -L https://www.atlassian.com/software/jira/downloads/binary/atlassian-jira-software-7.0.4-jira-7.0.4-x64.bin > /tmp/atlassian-jira-software-7.0.4-jira-7.0.4-x64.bin \
 && chmod 700 /tmp/atlassian-jira-software-7.0.4-jira-7.0.4-x64.bin \
 && bash /tmp/atlassian-jira-software-7.0.4-jira-7.0.4-x64.bin -q -varfile response.varfile \
 && rm /tmp/atlassian-jira-software-7.0.4-jira-7.0.4-x64.bin

ADD mysql-connector-java-5.1.34-bin.jar.zip /tmp/mysql-connector-java-5.1.34-bin.jar.zip

RUN unzip /tmp/mysql-connector-java-5.1.34-bin.jar.zip -d /opt/atlassian/jira/lib

ENTRYPOINT /bin/bash -c "/etc/init.d/jira start && sleep 2 && while true; do sleep 2; done"
