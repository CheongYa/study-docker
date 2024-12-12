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
* docker container run --publish 80:80 --detach(or -d) --name (container name) nginx:  
    docker 허브가 nginx 이미지를 찾고 사용하며 사용할 수 있는 새로운 컨테이너에서 새로운 프로세스를 실행시킨다.  
    80포트를 사용하여 80컨테이너와 매핑한다. nginx는 기본적으로 80포트를 사용한다.  
    --detach: 컨테이너를 분리하여 백그라운드에서 실행하도록 만든다. 
* docker container ls -a: docker 컨테이너의 파일과 폴더 명들을 전부 출력한다.
* docker container logs (container name): 최신 로그를 출력한다.
* docker container top (container name): (container name)컨테이너 안의 실행 중인 프로세스를 출력한다.
* docker container rm -f (container ID): (container ID)에 해당하는 컨테이너를 삭제한다. 여러개의 컨테이너 또한 동시에 삭제할 수 있다.  
-f 명령어를 사용하여 실행중인 컨테이너 또한 삭제할 수 있다.
* docker container run -d -p 3306:3306 --name (container name) -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql
* docker container logs (container name): 기록을 확인할 수 있다.
* docker container stop (container name): 실행중인 컨테이너를 종료시킬 수 있다.
* docker container top: 컨테이너 안에서 일어나는 일의 프로세스 목록을 확인할 수 있다.
* docker container inspect: 컨테이너가 어떻게 시작됐고 어떻게 구성됐는지에 대한 세부사항을 확인할 수 있다.
* docker container stats: 모든 컨테이너에 대한 정보와 각 컨테이너의 성능 통계를 실시간으로 확인할 수 있다.(단 name이 아닌 ID 형식으로 출력된다.)
* docker container run -it --name (container name) nginx bash(==shell name):
    - -i(interactive): 컨테이너의 표준 입력(STDIN)을 활성화하여 상호작용이 가능하게 만든다.
    - -t(tty): 가상 터미널을 할당하여 터미널 환경에서 컨테이너를 실행한다.
    - bash: 컨테이너 실행 시 기본 명령어로 bash 셸을 실행한다.
* docker container start -ai (container name): 종료된 -it로 생성한 컨테이너를 실행시킨다.
* docker container exec -it (container name) bash: 기존 컨테이너를 bash 형태로 실행시킨다.
* docker container run -p 80:80 --name (container name) -d nginx:
    - 호스트의 포트 80을 컨테이너의 포트 80에 매핑한다. 호스트의 포트 80으로 들어오는 트래픽이 컨테이너의 포트 80으로 전달됩니다.
* docker container port (container name): 포트 매핑 정보를 확인한다.
* docker container inspect --format '{{ .NetworkSettings.IPAddress }}' (container name): 네트워크 설정을 자세히 확인한다. --format 옵션을 사용하여 특정 정보를 출력하도록 지정할 수 있다. 여기서는 컨테이너의 IP 주소를 출력한다.
* docker network ls: 만들어진 모든 네트워크를 보여준다.
* docker network inspect (network name): 특정 네트워크에 대한 세부 사항을 보여준다.
* docker network create --driver: 내장된 드라이버와 타사 드라이버를 사용해 새 가상 네트워크를 생성하기 위해 지정할 수 있다.
* docker network disconnect: 연결 및 연결 해제 명령어.
* docker container run -d --name (container name) --network my_app_net nginx: 컨테이너를 my_app_net이라는 Docker 네트워크에 연결한다. 이를 이용해 같은 네트워크에 있는 컨테이너끼리 이름을 통해 통신할 수 있다.
* docker network connect (netwrok name) (container name): 동일 네트워크에 있는 것을 컨테이너 안에서 연결시킨다.
* docker container exec -it (container name1) ping (container name2): name1 컨테이너에서 name2 컨테이너로의 네트워크 연결 상태를 확인한다.
* docker container run -d --net dude --net-alias search elasticsearch:2: 새로운 컨테이너를 백그라운드에서 실행한다. dude라는 사용자 정의 docker 네트워크에 컨테이너를 연결하고 search라는 네트워크 별칭을 부여한다. 이것은 elasticsearch의 2버전 기반으로 컨테이너가 생성된다.
* docker container run --rm --net dude centos curl -s search:9200: 
    - curl -s search:9200: centos 컨테이너에서 curl 명령을 실행하여 search라는 컨테이너에 포트9200으로 http요청을 보낸다.


