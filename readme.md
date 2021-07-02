
<head>Docker</head></br>
도커에 대한 공부한 내용들을 적는 곳

1. WSL2 설치
2. Window Store에서 Windows Terminal 설치
3. WSL2 활성화 명령어 실행
  3-1. dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
  3-2. dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
4. window store에서 원하는 리눅스 버전 설치
  4-1. Ubuntu-18.04 LTS 
5. WSL2로 변환하기
  5-1. wsl --list --verbose
 </br>-> Name               state      version
     </br>Ubuntu-18.04 LTS   Running     1
6. wsl2를 기본 버전으로 설정  
  6-1. wsl --set-version Ubuntu-18.04 2
  6-2. wsl --set-default-version 2
  -> 변환이 진행 중입니다. 몇 분 정도 걸릴 수 있습니다...
    WSL 2와의 주요 차이점에 대한 자세한 내용은 https://aka.ms/wsl2를 참조하세요
    변환이 완료되었습니다. 
  </br>-> Name               state      version
     </br>Ubuntu-18.04 LTS   Running     2  
     
     
* 오류 해결
1. 가상 디스크 시스템 제한으로 인해 요청한 작업을 완료할 수 없습니다. 가상 하드 디스크 파일은 압축이 풀려 있는 상태이고 암호화되지 않아야 하며 스파스가 아니어야 합니다.     
-> UserName\AppData\Local\Package\CanonicalGroupLimited 폴더 우측 클릭, 고급탭 클릭, "내용을 압축하여 디스크 공간 절약" 및 "데이터 보호를 위해 내용을 암호화" 확인란이 선택 취소되어 있는지 확인


