# Week 2 과제 제출
___
## 1. HTTP
___
### HTTP의 정의, 특징
HTTP는 HyperText Transfer Protocol의 약자로 웹에서 서로 다른 시스템끼리
통신을 주고 받게 하는 규약이다.
HTTP는 서버가 클라이언트의 요청에 대한 응답을 마치면 연결을 끊어버리는
**비 연결성**과 연결을 끊음으로 인해 데이터가 유지될 수 없어 서버가 클라이언트의
정보를 저장할 수 없는 **무상태성**이 특징이다.

### HTTP연결 과정
HTTP의 연결과정은 이렇다.
1. 우선 클라이언트가 HTTP서버에 TCP연결을 시작한다.
2. HTTP서버는 연결을 수락하고 클라이언트에게 알린다.
3. 클라이언트는 HTTP메시지(오브젝트 요구)를 전송한다.
4. HTTP서버는 메시지를 받고 요청한 오브젝트를 포함한 응답 메시지를 소켓에 보낸다.
5. HTTP서버는 TCP연결을 해제한다.
6. 클라이언트는 객체가 포함된 응답 메시지를 받는다.

### 메소드와 상태코드
**HTTP Method**는 클라이언트가 서버에 요청을 보낼 때 그 요청의 목적과 종류를 알리기
위해 사용된다. Method는 GET, POST, PUT, PATCH, DELETE 등이 있다.

**HTTP 상태코드**는 서버에서 클라이언트의 요청에 대한 응답을 보낼 때 그 요청에 대한
처리 상태를 알려주는 기능을 한다. 코드는 100에서 500까지 세자리로 이루어져 있는데,
백의자리 숫자가 같은 코드끼리는 비슷한 의미를 지닌다.

## 2. HTTPS
___
### HTTPS란?
HTTPS는 쉽게 HTTP보다 보안이 더 강화된 버전이라고 생각하면 된다.

### HTTP와 비교
HTTP 메시지는 일반 텍스트이므로, 권한이 없는 당사자가 인터넷을 통해 쉽게 액세스하고
읽을 수 있다. 반면, HTTPS는 모든 데이터를 암호화된 형태로 전송한다. 따라서 민감한
데이터를 보호하기 위해서는 HTTP보다 HTTPS를 사용하는 것이 좋다.

## 3. URI 설계
___
- 이벤트 목록 조회
```text
GET /events
```
- 이벤트 조회
```text
GET /events/{eventID}
```
- 이벤트 등록
```text
POST /events
```
- 이벤트 수정
```text
PUT /events/{eventID}
```
- 이벤트 삭제
```text
DELETE /events/{eventID}
```
- 이벤트 상태 변경
```text
PATCH /events/{eventID}/status
```
- 특정 이벤트의 주문 목록 조회
```text
GET /events/{eventID}/orders
```
- 멤버 목록 조회
```text
GET /members
```
- 특정 멤버 권한 변경
```text
PATCH /members/{memberID}/authority
```
- 특정 멤버 정보 조회
```text
GET /members/{memberID}
```
- 특정 멤버 정보 변경
```text
PATCH /members/{memberID}
```
- 멤버 등록
```text
POST /members
```
