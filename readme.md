![docker-icon](./img/docker-icon.jpg)

# Docker 설치</br>
 도커에 대한 공부한 내용들을 적는 곳

>1. WSL2 설치
>2. Window Store에서 Windows Terminal 설치
>3. WSL2 활성화 명령어 실행
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
>4. window store에서 원하는 리눅스 버전 설치
```
Ubuntu-18.04 LTS 
```
>5. WSL2로 변환하기
```
wsl --list --verbose
```
```
Name               state      version
Ubuntu-18.04 LTS   Running     1
```     
>6. wsl2를 기본 버전으로 설정  
```
wsl --set-version Ubuntu-18.04 2
wsl --set-default-version 2
```
```
변환이 진행 중입니다. 몇 분 정도 걸릴 수 있습니다...
WSL 2와의 주요 차이점에 대한 자세한 내용은 https://aka.ms/wsl2를 참조하세요
변환이 완료되었습니다. 
```
```
Name               state      version
Ubuntu-18.04 LTS   Running     2  
```     
 >7. docker 사이트에서 docker 설치
 ```
 https://docs.docker.com/docker-for-windows/install/
 ```
     
* 오류 해결
>1. 가상 디스크 시스템 제한으로 인해 요청한 작업을 완료할 수 없습니다. 가상 하드 디스크 파일은 압축이 풀려 있는 상태이고 암호화되지 않아야 하며 스파스가 아니어야 합니다.     
-> UserName\AppData\Local\Package\CanonicalGroupLimited 폴더 우측 클릭, 고급탭 클릭, "내용을 압축하여 디스크 공간 절약" 및 "데이터 보호를 위해 내용을 암호화" 확인란이 선택 취소되어 있는지 확인



# Docker 사용</br>
### 기본 실행
```
docker run -it {이미지 이름} // docker hub에 업로드되어 있는 오피셜 이미지들을 가져와서 컨테이너로 만들어 사용 가능
```
### Dockerfile을 이용하여 커스텀 이미지 만들기
```
docker build -t {이미지 이름} .    <- 현재 위치에 Dockerfile이 없다면 상대경로 입력
```
### Dockerfile을 이용하여 컨테이너 만들기
```
docker run --name {컨테이너 이름} -v $(pwd):{볼륨 위치} -p 8080:8080 -d {이미지 이름}
```
### 컨테이너 중단
```
docker stop $(docker ps -aq)
```
### 컨테이너 삭제
```
docker rm $(docker ps -aq)
```
### 이미지 삭제 (사용중이지 않는 이미지들만)
```
docker image prune -a
```
### Docker 일괄 실행
```
docker-compose up -d(백그라운드 실행 = daemon) 
```
