# Docker

## 기초적인 개념

도커는 컨테이너를 관리하는 툴  
작은 가상환경이라고 생각하면 편안함  
하지만 가상환경은 커널까지 가상으로 구현을 한다면 컨테이너는 커널과 직접통신함

## 컨테이너 실행예제

아래 명령어를 실행하면 ubuntu를 가상으로 구현 가능함

```bash
docker run --rm -it ubuntu:20.04 bash
```