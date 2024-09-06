FROM jenkins/jenkins:lts-jdk17

USER root

# DNS 설정 추가
RUN echo "nameserver 8.8.8.8" > /etc/resolv.conf && \
    apt-get update && \
    apt-get install -y wget gnupg && \
    apt-get clean;

USER jenkins

# 환경 변수 설정
ENV JAVA_HOME /opt/java/openjdk
ENV PATH $JAVA_HOME/bin:$PATH

# Jenkins 시작 포인트
ENTRYPOINT ["/usr/bin/tini", "--", "/usr/local/bin/jenkins.sh"]