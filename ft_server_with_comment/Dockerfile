FROM	debian:buster
# 프로젝트 시작할 베이스 이미지를 debian:buster'로 설정

LABEL	maintainer="hann@student.42seoul.kr"
# 이미지에 메타데이터 추가

RUN	apt-get update && apt-get install -y \
	nginx \ # nginx 설치
	mariadb-server \
	php-mysql \
	php-mbstring \ # MariaDB(mysql) 설치
	openssl \ #openssl 설치
	vim \ # vim 설치
	wget \ # wget 설치
	php7.3-fpm # php 설치
 # 쉘 명령어를 실행하고 결과를 커밋

COPY	./srcs/run.sh ./
COPY	./srcs/default ./tmp
COPY	./srcs/wp-config.php ./tmp
COPY	./srcs/config.inc.php ./tmp
# HostOS의 파일 또는 디렉토리를 컨테이너 안의 경로로복사

EXPOSE	80 443
# 컨테이너가 80, 443포트를 사용할 예정임을 사용자에게 알림

CMD 	bash run.sh
# 생성된 컨테이너를 실행할 명령어를 지정
