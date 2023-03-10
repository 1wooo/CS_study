## 2.1 네트워크의 기초

1. 처리량과 지연시간

처리량(Throughput) - 링크를 통해 전달되는 단위 시간당 데이터양을 말함. 단위로는 bps(bits per second)를 씀. 트래픽, 네트워크 장치 간 대욕폭, 네트워크 중간에 발생하는 에러, 장치의 하드웨어 스펙에 영향을 받음.

대역폭 - 주어진 시간 동안 네트워크 연결을 통해 흐를 수 있는 최대 비트 수

지연 시간 (latency)  - 요청이 처리되는 시간을 말하며 어떤 메시지가 두 장치 사이를 왕복하는데 걸리는 시간. 매체 타입(유,무선), 패킷 크기, 라우터의 패킷 처리 시간에 영향을 받음.
2. 네트워크 토폴로지와 병목 현상

네트워크 토폴로지 - 네트워크를 설계할때 고려함. 노드와 링크가 어떻게 배치되어 있는지에 대한 방식이자 연결 형태를 말함.

1) 트리 토폴로지 - 계층형 토폴로지라고 하며 트리 형태로 배치된 네트워크 구성
2) 버스 토폴로지 - 중앙 통신 회선 하나에 여러개의 노드가 연결되어 공유하는 네트워크 구성. 근거리 통신망(LAN)에서 사용됨. 설치 비용이 적고 신뢰성이 우수하며 중앙 통신 회선에 노드를 추가하거나 삭제하기 쉬움. 그러나 스푸핑이 가능한 문제점이 있다.

스푸핑이란? - LAN상에서 송신부의 패킷을 송신과 관련없는 다른 호스트에 가지 않도록 하는 스위칭 기능을 마비시키거나 속여서 특정 노드에 해당 패킷이 오도록 처리하는것.

3) 스타 토폴로지 - 중앙에 있는 노드에 모두 연결된 네트워크 구성을 말함. 노드를 추가하거나 에러를 탐지하기 쉽고 패킷의 충동 가능성이 적음. 장애노드 발견이 쉬우며 장애노드가 중앙노드가 아닐 경우 다른 노드에 영향을 끼치는 것이 적음. 하지만 장애노드가 중앙노드일 경우에는 전체 네트워크가 마비됨. 설치비용이 고가임.

4) 링형 토폴로지 - 각각의 노드가 양 옆의 두 노드와 연결하여 전체적으로 고리처럼 하나의 연속된 길을 통해 통신을 하는 망 구성 방식. 각각의 노드는 고리 모양의 길을 통해 패킷을 처리함. 노드 수가 증가되어도 네트워크상의 손실이 거의 없고 충돌이 발생될 가능성이 적으며 노드의 고장 발견을 쉽게 찾을 수 있음. 하지만 네트워크 구성 변경이 어려우며 회선에 장애가 발생하면 전체 네트워크에 영향을 크게 끼치는 단점이 있음.

5) 메시 토폴로지 - 망형 토폴로지라고도 하며 그물망처럼 연결되어 있는 구조. 한 단말 장치에 장애가 발생해도 여러 개의 경로가 존재하므로 네트워크를 계속 사용할 수 있고 트래픽도 분산 처리가 가능함. 하지마 노드 추가가 어려우며 구축 비용과 운용 비용이 고가임.

병목 현상 - 전체 시스템의 성능이나 용량이 하나의 구성요소로 인해 제한을 받는 현상을 말함. 토폴로지가 중요한 이유는 병목 현상을 찾을 때 중요한 기준이 되기 때문. 
3. 네트워크 분류

네트워크는 규모를 기반으로 분류할 수 있음. 개인적으로 소유 가능한 규모. 즉 가장 작은 규모의 LAN(Local Area Network)와 서울시 등 시 정도의 규모인 MAN(Metropolitan Area Network). 그리고 세계 규모의 WAN(Wide Area Network)로 나눌 수 있음.

1) LAN - 근거리 통신망을 의미하며 같은 건물이나 캠퍼스 같은 좁은 공간에서 운영됨. 전송 속도가 빠르고 혼잡하지 않음.
2) MAN - 대도시 지역 네트워크를 나타냄. 전송속도는 평균이며 LAN보다는 더 많이 혼잡
3) WAN - 광역 네트워크를 의미하며 국가 또는 대륙 같은 더 넓은 지역에서 운영됨. 전송속도는 낮으며 매우 혼잡.
4. 네트워크 성능 분석 명령어

네트워크 병목 현상의 주된 원인은 다음과 같다.

1) 네트워크 대역폭
2) 네트워크 토폴로지
3) 서버 CPU, 메모리 사용량
4) 비효율적인 네트워크 구성

이때 테스트를 통해 ‘네트워크로부터 발생한 문제점’ 임을 확인한 후 네트워크 성능 분석을 해봐야 함. 이때 사용되는 명령어들은?

1) ping - 네트워크 상태를 확인하려는 대상 노드를 향해 일정 크기의 패킷을 전송하는 명령어임. 이를 통해 해당 노드의 패킷 수신 상태와 도달하기까지 시간 등을 알 수 있으며 해당 노드까지 네트워크가 잘 연결되어 있는지 확인 가능. ping은 TCP/IP 프로토콜 중 ICMP 프로토콜을 통해 도작함. 이 때문에 ICMP 프로토콜을 지원하지 않는 기기를 대상으로는 실행할 수 없거나 네트워크 정책상 ICMP나 traceroute를 차단하는 대상의 경우 ping 테스팅은 불가능함.

2) netstat - 접속되어 있는 서비스들의 네트워크 상태를 표시하는 데 사용되며 네트워크 접속, 라우팅 테이블, 네트워크 프로토콜 등 리스트를 보여줌. 주로 서비스의 포트가 열려 있는지 확인할 때 사용.

3) nslookup - DNS에 관련된 내용을 확인하기 위해 사용하는 명령어. 특정 도메인에 매핑된 IP를 확인하기 위해 사용

4) tracert - 리눅스에서는 traceroute임. 목적지 노드까지 네트워크 경로를 확인할 때 사용함. 목적지 노드까지 구간들 중 어느 구간에서 응답시간이 느려지는지 확인 가능.
5. 네트워크 프로토콜 표준화
IEEE802.3은 유선 LAN 프로토콜으로, 유선으로 LAN을 구축할 때 쓰이는 프로토콜임. 이를 통해 만든 기업이 서로 다른 장치끼리도 데이터를 송수신 할 수 있는 것임.
웹에 접속할 때 사용되는 HTTP 프로토콜도 있음. ‘서로 약속된’ 인터페이스인 HTTP라는 프로토콜을 통해 노드들은 웹 서비스를 기반으로 데이터를 주고받을 수 있음.

## 2.2 TCP/IP 4계층 모델

인터넷 프로토콜 스위트(internet protocol suite)는 인터넷에서 컴퓨터들이 서로 정보를 주고 받는 데 쓰이는 프로토콜의 집합임. 이를 TCP/IP 4계층 모델로 설명하거나 OSI 7 계층 모델로 설명하기도 함. TCP/IP 계층 모델은 네트워크에서 사용되는 통신 프로토콜의 집합으로 프로토콜의 네트워킹 범위에 따라 네 개의 추상화 계층으로 구성됨.

1. 계층 구조
TCP/IP 계층은 네 개의 계층을 가지고 있으며 OSI 7계층과 많이 비교함.
OSI 7계층은 TCP/IP 계층의 애플리케이션 계층을 3개로 쪼개고 링크 계층도 두개로 쪼갬. 또 TCP/IP의 인터넷 계층을 네트워크 계층으로 표현 함

이 계층들은 특정 계층이 변경되었을 때 다른 계층이 영향을 받지 않도록 유연하게 설계됨. 

1) 애플리케이션 계층 - FTP, HTTP, SSH, SMTP, DNS 등 응용프로그램이 사용되는 프로토콜 계층이며 웹 서비스, 이메일 등 서비스를 실질적으로 사람들에게 제공하는 층임.

FTP - 장치와 장치 간 파일을 전송하는 데 사용되는 표준 통신 프로토콜
SSH - 보안되지 않은 네트워크에서 네트워크 서비스를 안전하게 운영하기 위한 암호화 네트워크 프로토콜
HTTP - World Wide Web을 위한 데이터 통신의 기초이자 웹 사이트를 이용하는 데 쓰는 프로토콜
SMTP - 전자 메일 전송을 위한 인터넷 표준 통신 프로토콜
DNS - 도메인 이름과 IP 주소를 매핑해주는 서버. [www.naver.com](http://www.naver.com) 의 경우 Root DNS → .com DNS → .naver DNS → .www DNS 를 거쳐 완벽한 주소를 찾아 IP 주소를 매핑함.
    
    
    **전송계층** - 전송계층은 송신자와 수신자를 연결하는 통신 서비스를 제공하며 연결 지향 데이터 스트림 지원, 신뢰성, 흐름 제어를 제공함. 애플리케이션과 인터넷 계층 사이의 데이터가 전달 될 때의 중계 역학을 합니다. TCP, UDP 등이 있으며 대표적으로 TCP와 UDP가 있습니다.
    
    가상회선 패킷 교환 방식 - 각 패킷에는 가상회선 식별자갚 ㅗ함되며 모든 패킷을 전송하면 가상 회선이 해제되고 패킷들은 전송된 ‘순서대로’ 도착하는 방식을 말함.
    
    데이터그램 패킷 교환 방식 - 패킷이 독립적으로 이동하며 최적의 경로를 선택하여 감. 하나의 메시지에서 분할된 여러 패킷은 서로 다른 경로로 전송될 수 있으며 도착한 순서가 다를 수 있음. 
    
    TCP 연결 성립 과정 - TCP는 신뢰성 확보를 위해 3-way handshake 라는 작업을 진행함.
    
    1. 클라이언트는 서버에 클라이언트의 ISN을 담아 SYN을 보냄. ISN은 새로운 TCP 연결의 첫번째 패킷에 할당된 임의의 시퀀스 번호를 말하며 이는 장치마다 다를 수 있음.
    2. 서버는 클라이언트의 SYN을 수신하고 서버의 ISN을 보내며 승인번호로 클라이언트의 ISN+1 을 보냄.
    3. 클라이언트는 서버의 ISN+1 한 값인 승인번호를 담아 서버에 보냄.
    
    ISN - Initial Sequence Numbers 의 약어. 초기 네트워크 연결을 할 때 할당된 32비트 고유 시퀀스 번호임.
    
    TCP 연결 해재 과정 - 해제할때는 4-way handshake 과정.
    
    1. 클라이언트가 연결을 닫으려고 할 때 FIN으로 설정된 세그먼트를 전송. 이후 클라이언트는 FIN_WAIT_1상태로 서버의 응답을 기다림.
    2. 서버는 클라이언트로 ACK라는 승인 세그먼트를 보냄. 이후 CLOSE_WAIT 상태로 들어감. 클라이언트가 해당 ACK를 받으면 클라이언트는 FIN_WAIT_2 상태가 됨.
    3. 서버는 ACK를 보내고 일정 시간 이후에 클라이언트에 FIN을 전송.
    4. 클라이언트는 서버의 FIN을 받고 TIME_WAIT 상태가 되고 다시 서버로 ACK를 보냄. 서버는 해당 ACK를 받고 CLOSED상태가 됨. 이후 클라이언트는 일정 시간을 대기한 후 연결을 닫고 클라이언트와 서버의 모든 자원 연결이 해제됨.
    
    왜 일정 시간을 대기하고 연결을 닫을까? 
    
    1. 지연 패킷이 발생할 경우 대비. 패킷이 뒤늦게 도착하여 이를 처리하지 못하면 데이터 무결성 문제가 발생함
    2. 두 장치가 연결이 닫혔는지 확인하기 위해서임. 서버가 LAST_ACK 상태일때 클라이언트가 연결을 닫게 된다면 다시 클라이언트가 해당 서버와 연결을 시도할때 서버는 아직 LAST_ACK 상태이므로 접속 오류가 발생함.
    
    **인터넷 계층** 
    
    장치로부터 받은 네트워크 패킷을 IP 주소로 지정된 목적지로 전송하기 위해 사용되는 계층임. IP,ARP,ICMP 등이 있으며 패킷을 수신해야 할 상대의 주소를 지정하여 데이터를 전달함. 상대방이 제대로 받았는지에 대해 보장하지 않는 비연결적인 특징을 가지고 있음.
    
    **링크 계층**
    
    전선, 광섬유, 무선 등 실질적으로 데이터를 전달하며 장치 간에 신호를 주고받는 ‘규칙’을 정하는 계층. 네트워크 접근 계층이라고도 함. 이를 물리 계층과 데이터 링크 계층으로 나누기도 하는데 물리 계층은 무선 LAN과 유선 LAN을 통해 0과 1로 이뤄진 데이터를 보내는 계층을 말하며, 데이터 링크 계층은 ‘이더넷 프레임’을 통해 에러 확인, 흐름 제어. 접근 제어를 담당하는 계층을 말함.
    
    전이중화 통신 - 듀플렉스라고도 하며 양쪽 장치가 서로 동시에 송수신을 할 수 있는 방식을 말함. 송신로와 수신로를 분리해서 데이터를 주고받으며 현대의 고속 이더넷은 이를 기반으로 설계됨.
    
    이더넷 프레임 - 데이터 링크 계층은 이더넷 프레임을 통해 전달받은 데이터의 에러를 검출하고 캡슐화 함.
    
    - Preamble: 이더넷 프레임이 시작임을 알립니다.
    - SFD(Start Frame Delimiter): 다음 바이트부터 MAC 주소 필드가 시작됨을 알립니다.
    - DMAC, SMAC: 수신, 송신 MAC 주소를 말합니다.
    - EtherType: 데이터 계층 위의 계층인 IP 프로토콜을 정의합니다. 예를 들어 IPv4 또는 IPv6가 됩니다.
    - Payload: 전달받은 데이터
    - CRC: 에러 확인 비트
    
    MAC 주소 - 컴퓨터나 노트북의 LAN카드 식별번호. 6바이트로 구성됨.
