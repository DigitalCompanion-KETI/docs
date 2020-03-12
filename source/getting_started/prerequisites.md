# Prerequisites

자신의 온프레미스 혹은 클라우드 환경에서 Digital Companion Framework를 구축하기 위해서는 아래와 같은 환경이 구축되어있어야 한다.



- Kuberntes (>= v1.15.2) or Minikube (>= v1.4.0)
- Python (2.x or 3.x)
- Golang (>= v1.12.5)
- grpc (>=v1.25.0)
- grpc-gateway ( >= v1.14.3)
- protobuf (>= v1.4.0-rc.4)
- protocol buffers (>= v3.7.1)
- protoc-gen-go (>= v1.2.0)
- grpc-tools
- protoc plugin



## Go

[공식 Go 다운로드 홈페이지](https://golang.org/doc/install)에서 설치파일을 다운로드 받는다.

설치파일을 압축해제하고, `/user/local`로 위치를 옮긴다.

```
$ sudo tar -xvf go1.12.5.linux-amd64.tar.gz
$ sudo mv go /usr/local
```



`.bashrc`파일을 수정하여 go 관련 환경변수를 설정한다.

```
$ vim ~/.bashrc
>>
# add this lines
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
```



변경한 환경변수를 적용한다.

```
$ source ~/.bashrc
```



설치 내용을 확인한다.

```
$ go version
$ go env
```



## gRPC

gRPC관련 go package를 다운받는다.

```
$ go get -u google.golang.org/grpc
# $ go get -u golang.org/x/net
$ go get -u golang.org/x/sys/unix
```



## gRPC-gateway

gRPC-gateway관련 go package를 다운받는다.

```
$ go get -u github.com/kardianos/govendor
$ cd $GOPATH/src
$ govendor init
$ govendor fetch github.com/googleapis/googleapis/google/api
$ cd $GOPATH/src/github.com/golang/protobuf
$ git checkout master
$ go get -u github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway
$ go get -u github.com/grpc-ecosystem/grpc-gateway/protoc-gen-swagger
$ go get -u github.com/golang/protobuf/protoc-gen-go
```



## protocol buffers

protocol buffer관련 패키지를 다운받는다.

```
$ curl -OL https://github.com/protocolbuffers/protobuf/releases/download/v3.7.1/protoc-3.7.1-linux-x86_64.zip
$ unzip protoc-3.7.1-linux-x86_64.zip -d protoc3

$ sudo mv protoc3/bin/* /usr/local/bin/
$ sudo mv protoc3/include/* /usr/local/include/

$ sudo chown $USER /usr/local/bin/protoc
$ sudo chown -R $USER /usr/local/include/google

$ export PATH=$PATH:/usr/local/bin
```



## Protoc-gen-go

protoc-gen-go를 설치한다.

```
$ cd $GOPATH/src/github.com/golang/protobuf/protoc-gen-go
$ git checkout tags/v1.2.0 -b v1.2.0
$ go install
```



## gRPC tools

gRPC tools을 설치한다.

```
$ pip install grpcio-tools
$ pip3 install grpcio-tools
```



## protoc plugin

protoc plugin을 설치하고 환경변수를 설정한다.

```
$ go get -u github.com/golang/protobuf/{proto,protoc-gen-go}
$ export PATH=$PATH:$GOPATH/bin
```



## dep

go package manager인 dep를 설치한다.

```
$ go get -u github.com/golang/dep/cmd/dep
```



