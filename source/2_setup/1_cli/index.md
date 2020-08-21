DCF CLI Setup
====================================



DCF의 CLI(Command line interface)는 다음과 같은 기능을 지원합니다

- 함수 런타임 지원목록 확인
- 함수 생성
- 함수 빌드
- 함수 테스트
- 함수 배포
- 함수 삭제
- `함수 호출
- 함수의 로그 확인 



DCF CLI를 사용하는 방법이 궁금하시다면, [Deploying Functions](), [CLI Reference]()를 참고하시면 됩니다



## Prerequisite

CLI 설치를 위해서는 아래 의존성 소프트웨어가 설치되어있어야합니다



- [Docker >= 19.03](https://docs.docker.com/v17.09/engine/installation/linux/docker-ce/ubuntu/)
- [Nvidia-Docker2](https://github.com/nvidia/nvidia-docker/wiki/Installation-(version-2.0))

- [golang >= 1.12](https://golang.org/dl/)



> Nvidia-Docker2는 컴퓨터의 그래픽 드라이버 버전에 따라서 CUDA 버전의 제한이 있습니다. 
>
> [Nvidia-Docker의 Requirements](https://github.com/NVIDIA/nvidia-docker/wiki/CUDA#requirements)를 확인하시고, 그래픽 드라이버를 업그레이드 해주시기 바랍니다



## Installation

DCF CLI는 [DCF Releases의 Assets](https://github.com/DigitalCompanion-KETI/DCFramework/releases)에서 실행파일로 제공되며, 아래 명령어로 간단하게 설치할 수 있습니다

```bash
$ wget https://github.com/DigitalCompanion-KETI/DCFramework/releases/download/v1.0.0/dcf-cli
$ sudo chmod 777 dcf-cli
$ mv dcf-cli /usr/bin
```



설치를 완료하였다면, 아래 명령어를 통해서 DCF CLI가 잘 작동하는지 확인해볼 수 있습니다

```bash
$ dcf-cli version
>>
Version: 0.1.0
```

