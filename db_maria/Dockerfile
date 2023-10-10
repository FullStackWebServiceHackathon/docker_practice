# https://nasn.tistory.com/116
# mariadb 10.6 버전 이미지 사용.
FROM mariadb:10.11.5-jammy

# 비밀번호 설정
ENV MYSQL_ROOT_PASSWORD 1234

# WORKDIR /etc/mysql
# RUN mkdir setDB
# WORKDIR /etc/mysql/setDB

# 초기 세팅 SQL 파일 Docker로 Copy
# COPY ./Config/setDB.sql /etc/mysql/setDB/setDB.sql

# MariaDB Config Setting (table 소문자, 한국 시간, 한글 깨짐 수정 등)
RUN echo lower_case_table_names=1 >> /etc/mysql/conf.d/docker.cnf
RUN echo default-time-zone='+9:00' >> /etc/mysql/conf.d/docker.cnf
RUN echo collation-server = utf8mb4_unicode_ci >> /etc/mysql/conf.d/docker.cnf
RUN echo collation-server = utf8mb4_0900_ai_ci >> /etc/mysql/conf.d/docker.cnf
RUN echo character-set-server = utf8mb4 >> /etc/mysql/conf.d/docker.cnf
RUN echo skip-character-set-client-handshake >> /etc/mysql/conf.d/docker.cnf

# git 설치
RUN apt-get update
RUN apt-get install git -y

# 1. Dockerfile을 먼저 빌드해주세요
#   docker build -t db_maria .
# 2. 만들어진 이미지를 이용해서 docker container를 만들어주세요
#   docker run -it -d --name db_maria -p 3306:3306 db_maria