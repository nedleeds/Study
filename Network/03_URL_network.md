## 🥕 웹 통신의 흐름

### 🌿 웹이란 ?

`WWW(World Wide Web)` 의 약자이며 인터넷으로 연결된 컴퓨터를 통해 정보를 공유할 수 있는 공간을 뜻한다.

흔히들 `( 웹 )`과 `( 인터넷 )`을 통용하여 사용하는데 엄연히 다른 개념이다.

---

[참고] 웹과 인터넷의 차이

`WWW(World Wide Web)`은 컴퓨터가 서로 연결되어 통신을 주고받는, 컴퓨터끼리의 네트워크

`웹`은 인터넷으로 연결된 컴퓨터를 통해 정보를 공유할 수 있는 무형의 정보 네트워크

---

### 🌿 웹 통신

기본적으로 웹 통신은 `( HTTP )` 프로토콜을 사용한다.

통신의 주체를 크게 `( 클라이언트 )`와 `( 서버 )`로 나눌 수 있다.

- `( 클라이언트 )`: 서버에게 정보를 요청하거나 접속하고자 하는 주체 → **Request**
  - ex) 브라우저
- `( 서버 )` : 클라이언트에게 정보 혹은 서비스를 제공하는 컴퓨터 (혹은 시스템) → **Response**

---

### 🌿 웹 통신 세부과정

`https://www.naver.com/` 주소창에 해당 URL을 입력한 뒤 클라이언트에 화면이 렌더링 되기까지 어떤 과정이 있을까?

- `( IP주소 )`란, 컴퓨터들의 고유 식별번호라고 할 수 있는데, `127.0.0.1`과 같은 형태의 숫자로 나타난다.
  > 현재는 .으로 구분된 각 자리에서 0~255를 나타낼 수 있는 32비트의 `( IPv4 )` 프로토콜을 사용하나, 인터넷 사용자 수 증가로 IP주소 부족 현상이 일어났고 이는 128비트의 `( IPv6 )`가 등장하는 배경이 되었다. ( 2dfc : 0 : 0 : 0 : 0217 : cbff : fe8c : 0 )
- `( 도메인 이름 )`이란, 사람이 쉽게 외울 수 있도록 IP주소를 어떠한 문자로 표현한 것을 의미한다. 즉, 위 URL에서 `naver.com`이 이것에 해당한다.

---

- 네이버의 IP 주소 알아내기
  - windows 기준 cmd창에 **tracert [naver.com](http://naver.com/)** 을 입력하면 IP주소를 알아낼 수 있다.
  - 검색창에 **223.130.195.200** 을 입력하면 www.naver.com을 입력했을때와 동일하게 접속 가능
  - [https://ko.wikihow.com/웹사이트의-IP-주소를-찾는-법](https://ko.wikihow.com/%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%9D%98-IP-%EC%A3%BC%EC%86%8C%EB%A5%BC-%EC%B0%BE%EB%8A%94-%EB%B2%95) ← mac의 경우 참고

---

브라우저에 입력된 도메인 이름을 통해 **해당 도메인의 IP주소를 얻은 뒤** 통신을 시작할 수 있다.

이러한 `도메인 이름 -> IP 주소` 과정에서 필요한 도우미 역할을 하는 것이 `DNS(도메인 이름 시스템) `이다.

-------

![웹통신흐름](https://user-images.githubusercontent.com/62277179/184580500-aeb96b38-039b-44d8-93ee-d945ae672b64.png)
    
------


- **웹 통신 작동 과정**
  1. 사용자가 **도메인 이름** 입력
  2. **DNS**를 통해 도메인 이름과 매핑되는 IP주소 획득
  3. **HTTP** 프로토콜을 사용하여 요청 `(=HTTP Request)` 생성
  4. **TCP** 프로토콜을 사용하여 **서버의 IP주소 컴퓨터**로 Request 전송
  5. 서버가 클라이언트의 **요청**에 대한 **응답** `(=HTTP Response)` 전송
  6. 브라우저에 도착한 Response는 **웹페이지를 나타내는 데이터**로 변환되어 브라우저에 나타남.
