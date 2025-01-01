## 네트워크 프래그래밍과 소켓의 이해
### 소켓이란?
        운영체제에서 제공하는 네트워크 망의 연결에 사용되는 도구이다.
### 소켓 함수
```c
// 소켓을 생성하는 함수
#include <sys/socket.h>

int socket(int domain, int type, int protocol);
// 성공 시 return file descriptor;
// 실패 시 return -1;
```
```c
// IP, PORT 할당하는 함수
#include <sys/socket.h>

int bind(int sockfd, struct sockaddr* myaddr, socklen_t addrlen);
// 성공 시 return 0;
// 실패 시 return -1;
```
```c
// 네트워크 연결을 허용하는 함수
#include <sys/socket.h>

int listen(int sockfd, int backlog);
// 성공 시 return 0;
// 실패 시 return -1;
```
```c
// 네트워크 연결을 수락하는 함수
#include <sys/socket.h>

int accept(int sockfd, struct sockaddr* addr, socklen_t* addrlen);
// 성공 시 return file descriptor;
// 실패 시 return -1;
```
```c
// 네트워크 연결을 요청하는 함수
#include <sys/socket.h>

int connet(int sockfd, struct sockaddr* serv_addr, socklen_t addrlen);
// 성공 시 return 0;
// 실패 시 return -1;
```