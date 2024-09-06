FROM jenkins/jenkins:lts-jdk17

USER root

# 필수 패키지 설치
RUN apt-get update && \
    apt-get install -y wget gnupg2 && \
    apt-get clean;

# 필요한 경우 추가 설정이나 패키지 설치
# 예: Git 또는 기타 필요한 도구들
# RUN apt-get install -y git

USER jenkins

# 환경 변수 설정 (이미 JDK 17이 설치되어 있음)
ENV JAVA_HOME /opt/java/openjdk
ENV PATH $JAVA_HOME/bin:$PATH

# Jenkins 시작 포인트
ENTRYPOINT ["/usr/bin/tini", "--", "/usr/local/bin/jenkins.sh"]
