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
* docker ps (or docker container ls): 현재 사용중인 컨테이너들을 보여준다.
* docker command line 구조
    - old(still works): docker <command> (options)
    - new: codker <command> <sub-command> (options)
* docker container run --publish 80:80 --detach(or -d) --name (name) nginx:  
    docker 허브가 nginx 이미지를 찾고 사용하며 사용할 수 있는 새로운 컨테이너에서 새로운 프로세스를 실행시킨다.  
    80포트를 사용하여 80컨테이너와 매핑한다. nginx는 기본적으로 80포트를 사용한다.  
    --detach: 컨테이너를 분리하여 백그라운드에서 실행하도록 만든다. 
* docker container ls -a: docker 컨테이너의 파일과 폴더 명들을 전부 출력한다.
* docker container logs webhost: 웹호스트의 최신 로그를 출력한다.
* docker container top (name): (name)컨테이너 안의 실행 중인 프로세스를 출력한다.
* docker container rm -f (container ID): (container ID)에 해당하는 컨테이너를 삭제한다. 여러개의 컨테이너 또한 동시에 삭제할 수 있다.  
-f 명령어를 사용하여 실행중인 컨테이너 또한 삭제할 수 있다.
* docker container run -d -p 3306:3306 --name (name) -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql
* docker container logs (name): 기록을 확인할 수 있다.
* docker container stop (name): 실행중인 컨테이너를 종료시킬 수 있다.
* docker container top: 컨테이너 안에서 일어나는 일의 프로세스 목록을 확인할 수 있다.
* docker container inspect: 컨테이너가 어떻게 시작됐고 어떻게 구성됐는지에 대한 세부사항을 확인할 수 있다.
* docker container stats: 모든 컨테이너에 대한 정보와 각 컨테이너의 성능 통계를 실시간으로 확인할 수 있다.(단 name이 아닌 ID 형식으로 출력된다.)
* docker container run -it --name (name) nginx bash(==shell name):
    - -i(interactive): 컨테이너의 표준 입력(STDIN)을 활성화하여 상호작용이 가능하게 만든다.
    - -t(tty): 가상 터미널을 할당하여 터미널 환경에서 컨테이너를 실행한다.
    - bash: 컨테이너 실행 시 기본 명령어로 bash 셸을 실행한다.
* docker container start -ai (name): 종료된 -it로 생성한 컨테이너를 실행시킨다.
* docker container exec -it (name) bash: 기존 컨테이너를 bash 형태로 실행시킨다.
