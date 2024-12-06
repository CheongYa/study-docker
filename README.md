# study-docker

## 설치 환경
* Windows 11
* Docker
* Ubuntu
* VSCode
    - Docker
    - Kubernetes
    - Remote Development(SSH, Tunnels, Explorer, WSL)

## Docker 명령어
* docker: docker의 Commands가 출력된다.
* docker version: docker의 Version, API Version, OS/Arch 등이 출력된다.
* docker info: 엔진을 위한 구성과 셋업 등 많은 세부사항이 출력된다. (컨테이너 수, 이미지의 수 등)
* docker command line 구조
    - old(still works): docker <command> (options)
    - new: codker <command> <sub-command> (options)
* docker container run --publish 80:80 --detach --name (name) nginx:  
    docker 허브가 nginx 이미지를 찾고 사용하며 사용할 수 있는 새로운 컨테이너에서 새로운 프로세스를 실행시킨다.  
    80포트를 사용하여 80컨테이너와 매핑한다. nginx는 기본적으로 80포트를 사용한다.  
    --detach 명령어를 사용하여 백그라운드에서 실행하도록 만든다. 
* docker container ls -a: docker 컨테이너의 파일과 폴더 명들을 전부 출력한다.
* docker container logs webhost: 웹호스트의 최신 로그를 출력한다.
* docker container top (name): (name)컨테이너 안의 실행 중인 프로세스를 출력한다.
* docker container rm -f (container ID): (container ID)에 해당하는 컨테이너를 삭제한다. 여러개의 컨테이너 또한 동시에 삭제할 수 있다.  
-f 명령어를 사용하여 실행중인 컨테이너 또한 삭제할 수 있다.
