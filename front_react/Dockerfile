# nodejs가 포함된 도커이미지 만들기
FROM node:18-alpine3.17
MAINTAINER Kim Daekyu <narwhal_blast@naver.com>

# git 설치하기 (alpine에서는 apk를 이용해서 패키지를 설치함)
RUN apk update
RUN apk upgrade
RUN apk add git

# 1. Dockerfile을 먼저 빌드해주세요
#   docker build -t react_node .
# 2. 만들어진 이미지를 이용해서 docker container를 만들어주세요
#   docker run -it -d --name front_react -v `pwd`:/web_react -p 80:3000 react_node