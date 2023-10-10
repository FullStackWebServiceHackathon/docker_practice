MAINTAINER Kim Daekyu <narwhal_blast@naver.com>
# java 빌드 및 jar실행이 가능한 도커 이미지 만들기
FROM ubuntu:18.04
# bash 사용하기
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# 필요한 패키지 설치하기 (alpine에서는 apk를 이용해서 패키지를 설치함)
RUN apt-get update
# JDL설치 >> JDK설치 도중 y를 입력해야 하기 때문에 -y옵션 추가
RUN apt-get install openjdk-17-jdk -y

# JAVA-HOME 환경변수 설정
RUN echo "PATH=\"/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin\"" >> /etc/environment
RUN echo "JAVA_HOME=\"/usr/lib/jvm/java-17-openjdk-amd64\"" >> /etc/environment

# 환경변수 업데이트를 위한 source명령어는 bash에서만 실행 가능
RUN source /etc/environment

# git 설치
RUN apt-get install git -y

# 1. Dockerfile을 먼저 빌드해주세요
#   docker build -t spring_jdk .
# 2. 만들어진 이미지를 이용해서 docker container를 만들어주세요
#   docker run -it -d --name front_react -v `pwd`:/web_react -p 80:3000 react_node