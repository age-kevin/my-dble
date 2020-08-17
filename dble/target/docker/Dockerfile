FROM centos:centos7
RUN yum install -y wget java mysql

#RUN wget -P /opt https://github.com/age-kevin/dble/blob/master/dble-2.19.11.0-20200729164505-linux.tar.gz && \
#    tar zxvf /opt/dble-2.19.11.0-20200729164505-linux.tar.gz -C /opt && \
#    wget https://github.com/age-kevin/dble/blob/master/dble/docker-images/quick-start/schema.xml -P /opt/dble/conf/ && \
#    wget https://github.com/age-kevin/dble/blob/master/dble/docker-images/quick-start/server.xml -P /opt/dble/conf/ && \
#    wget https://github.com/age-kevin/dble/blob/master/dble/docker-images/quick-start/rule.xml -P /opt/dble/conf/ && \
#    wget https://github.com/age-kevin/dble/blob/master/dble/docker-images/quick-start/wrapper.conf -P /opt/dble/conf/ && \
#    wget https://github.com/age-kevin/dble/blob/master/dble/docker-images/quick-start/docker_init_start.sh -P /opt/dble/bin/ && \
#    wget https://github.com/age-kevin/dble/blob/master/dble/docker-images/wait-for-it.sh -P /opt/dble/bin/ && \
#    chmod 777 /opt/dble/bin/* && \
#    rm -f /opt/dble-2.19.11.0-20200729164505-linux.tar.gz

COPY dble-2.19.11.0-20200729164505-linux.tar.gz /opt
COPY quick-start/schema.xml /opt/dble/conf/
COPY quick-start/server.xml /opt/dble/conf/
COPY quick-start/rule.xml /opt/dble/conf/
COPY quick-start/wrapper.conf /opt/dble/conf/
COPY quick-start/docker_init_start.sh /opt/dble/bin/
COPY wait-for-it.sh /opt/dble/bin/

RUN tar zxvf /opt/dble-2.19.11.0-20200729164505-linux.tar.gz -C /opt && \
    chmod 777 /opt/dble/bin/* && \
    rm -f /opt/dble-2.19.11.0-20200729164505-linux.tar.gz

VOLUME /opt/dble

CMD ["/opt/dble/bin/docker_init_start.sh"]
