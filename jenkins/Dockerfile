FROM jenkins/jenkins:lts-jdk17

USER root

# 미러 변경 및 필요한 패키지 설치
RUN sed -i 's|http://deb.debian.org|http://ftp.us.debian.org|' /etc/apt/sources.list && \
    apt-get update && \
    apt-get install -y wget gnupg && \
    apt-get clean;

USER jenkins

# 환경 변수 설정
ENV JAVA_HOME /opt/java/openjdk
ENV PATH $JAVA_HOME/bin:$PATH

# Jenkins 시작 포인트
ENTRYPOINT ["/usr/bin/tini", "--", "/usr/local/bin/jenkins.sh"]