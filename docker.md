# Docker

## 기초적인 개념

도커는 컨테이너를 관리하는 툴이다.

작은 가상환경이라고 생각하면 편안하다.

하지만 가상환경은 커널까지 가상으로 구현을 한다면 컨테이너는 커널과 직접통신한다.

## 컨테이너 실행예제

아래 명령어를 실행하면 ubuntu를 가상으로 구현 가능하다.

```bash
docker run --rm -it ubuntu:20.04 bash
```

여기서 ubuntu 는 이미지 이름이고 :20.04는 태그 명칭이다.

## 이미지 빌드 방법

#### __`Dockerfile`__

```Dockerfile
FROM ubuntu:20.04
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install --no-install-recommends -y nginx=1.18.0-0ubuntu1 \
    && rm -rf /var/lib/apt/list/
```

위 파일을 생성한다.

아래 주석을 잘 참고하여 이미지를 빌드하도록 하자.

```bash
# __username__: 유저이름
# __image_name__: 이미지 이름
# __version__: 버전 선택 기본적으로 latest 지정됨

docker build -t __username__/__image_name__:__version__ -f Dockerfile .
```

## 도커 계정인증

계정 인증 방식이 token 형식으로 바뀌었다.

dockerhub 으로 들어가서 유저 아이디를 클릭한후 Account Settings > Security > New Access Token 으로 토큰을 발행하여 사용한다.

```bash
docker login
```

## 이미지 푸시 방법

```bash
# __username__: 유저이름
# __image_name__: 이미지 이름
# __version__: 버전 선택 기본적으로 latest 지정됨

docker push __username__/__image_name__:__version__
```
