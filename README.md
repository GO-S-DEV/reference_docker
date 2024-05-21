# 네트워크 생성
docker network create <네트워크 이름>

# Windows 개발 환경
docker-compose -f local.docker-compose.yml --env-file local.env up -d --build
# nginx 볼륨에 추가
docker-compose -f local.docker-compose.yml --env-file local.env down -d

# elastic 따로
docker-compose -f elastic.docker-compose.yml --env-file local.env up -d --build


# redis 따로
docker-compose -f elastic.docker-compose.yml --env-file local.env up -d --build

# 개발 환경
docker network create <네트워크 이름>
docker-compose --env-file development.env up -d
docker-compose --env-file development.env down -d
docker-compose -f redis.docker-compose.yml --env-file development.env up -d --build
docker-compose -f elastic.docker-compose.yml --env-file development.env up -d --build


# 실제 배포 환경
docker network create <네트워크 이름>
docker-compose --env-file production.env up -d
docker-compose --env-file production.env down -d
