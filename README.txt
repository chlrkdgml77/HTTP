< HTTP >

1. 인터넷 네트워크
  - 인터넷에서 컴퓨터-컴퓨터 or 클라이언트-서버는 어떻게 통신할까?
  A. IP
	1) IP란?
	  -> 인터넷에 연결되어 있는 모든 장치들을 식별할 수 있도록 각각의 장치들에 부여되는 고유 주소
	2) IP의 역할
	  -> 지정한 IP주소에 데이터 전달
	  -> 패킷이라는 통신 단위로 데이터 전달
	3) IP 패킷 구조
	  -> 목적인 “전송 데이터”를 감싸고 있는 형태로 출발지IP, 도착지IP등의 내용들을 포함하고 있다.
	4) 결론
	  -> 클라이언트에서 전송 데이터를 IP패킷으로 감싸서 서버에 보내고 서버가 받으면 응답 데이터를 IP패킷으로 감싸서 클라이언트에게
	5) 한계
	  - 비연결성
	    -> 패킷을 받을 대상이 없거나 서비스 장애가 일어나도 패킷 전송
 	  - 비신뢰성
	    -> 중간에 패킷이 사라질 가능성 있음
	    -> 패킷 도착 순서가 내 의도와 다를 수 있음
	  - 프로그램 구분
	    -> 같은 IP를 사용하는 애플리케이션이 2개 이상이면 어디에 
		보낼지 구분은 어떻게?
	  => 이러한 문제를 해결하기 위해 TCP, UDP 등장
  
  B. TCP, UDP
	1) 인터넷 프로토콜 스택의 4계층
	  - 애플리케이션 계층 -> HTTP
	  - 전송 계층 -> TCP, UDP
	  - 인터넷 계층 -> IP
	  - 네트워크 인터페이스 계층
	2) 현재 데이터 전송 과정
	  a. 애플리케이션(클라이언트)가 전송 데이터 생성
	  b. SOCKET 라이브러리를 통해 전달
	  c. TCP 정보가 생성되고 그것이 전송 데이터를 감쌈
	    -> TCP 정보: 출발지 PORT, 목적지 PORT, ...
	  d. c를 IP패킷이 다시 한번 감쌈
	  e. 네트워크 인터페이스를 통해 서버로 전달
	3) TCP 특징
	  - TCP 3 way handshake(가상 연결)
	    - 클라이언트가 서버에 SYN(접속 요청)을 보냄 -> 서버에서 SYN	받으면 클라이언트에 SYN과 ACK(요청 수락)을 보냄->클라이언트가 해당 메시지를 받으면 마지막으로 ACK을 보냄
	  - 데이터 전달 보증
	  - 순서 보장
	  - PORT 기능 -> 같은 IP를 사용하는 애플리케이션 구분해주는 기능
	4) UDP 특징
	  - TCP 특징에서 PORT 기능만을 갖고 있음
	    -> 그러면 왜 사용?
		-> 단순하고 빠름 + 기능이 적은만큼 확장성이 넓음
	5) DNS
	  - IP의 문제를 보완하는 기능
	   -> IP는 기억하기 어렵다
	   -> IP는 변경될 수 있다.
	  - DNS 서버에서 IP주소에 도메인명을 할당하고 클라이언트가 도메인명을 검색하면 IP주소를 반환해줌

	 
