FROM jenkins/jenkins:lts-jdk11

USER root

# Java 17 설치
RUN apt-get update && \
    apt-get install -y openjdk-17-jdk && \
    apt-get clean;

# Jenkins 사용자에게 소유권 변경
RUN chown -R jenkins:jenkins /usr/lib/jvm

USER jenkins

# 환경 변수 설정
ENV JAVA_HOME /usr/lib/jvm/java-17-openjdk-amd64
ENV PATH $JAVA_HOME/bin:$PATH

# Jenkins 시작 포인트
ENTRYPOINT ["/usr/bin/tini", "--", "/usr/local/bin/jenkins.sh"]
