# 💻 Tcp 3-way handshake 란❓❓

- tcp 장치들 사이에 논리적인 접속을 성립 하기 위하여 3-way-handshake를 사용한다.
- tcp의 연결을 초기화 할 때 사용한다.
- tcp/ip 프로토콜을 이용해서 통신을 하는 응용프로그램이 데이터를 전송하기 전에 먼저 정확한 전송을 보장하기 위해 상대방 컴퓨터와 사전에 세션을 수립하는 과정
- SYN, ACK 패킷을 주고 받는다.
- 임의의 난수를 SYN의 플래그에 전송하고, 그것을 받은 측은 ACK의 플래그에 1을 더한 값을 전송.
    - 여기서 난수를 사용하는 이유? 기존 요청과 구분하기 위한 플래그로 사용.
    - 

client > server : TCP SYN

server > client : TCP SYN ACK

client > server : TCP ACK

 * 여기서 SYN은(synchronize sequence numbers)   ACK(acknowledgment)의 약어다.*

## ✨ 역할 ✨

- 양쪽 모두 데이터를 전송할 준비가 되었다는 것을 보장하고, 실제로 데이터 전달이 시작하기전에   한쪽이 다른 한쪽이 준비되었다는 것을 알 수 있도록 한다.
- 양쪽 모두 상대편에 대한 초기 순차일련변호를 얻을 수 있도록 한다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/597be500-75c4-4d2d-b009-69458d648fd3/Untitled.png)

## ✨ 순서 ✨

 = **SYN(n) -> ACK(n+1), SYN(m) -> ACK(m+1)**

1.  클라이언트가 서버에 접속 요청을 하는 SYN 패킷을 보낸다. 

       |  이때 클라이언트는 SYN을 보내고 SYN/ACK 응답을 기다리는 SYN_SENT 상태가 된다.

1. 서버가 SYN 요청을 받고  클라이언트에게 요청 👌(수락) 한다는 ACK,SYN flag 가 설정된 패킷을 발송하고 A가 다ㅋ

1. 클라이언트는 서버에 ACK를 보내고 이후 부터는 연결이 이루어지고 데이터가 오고 가게 된다.

이때 서버의 상태가 ESTABLISHED이다.

                         

이와 같이 1~3 단계 까지의 단계를 거치기 때문에 3-way handshake 라고 부른다.

 

# 💻 Tcp 4-way handshake 란❓❓

- 3-way handshake가 tcp 연결을 초기화 할때 사용 한다면, 4way는 세션을 종료하기 위해 수행되는 절차

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/65f5ff41-8188-4e58-8afa-f84ab0d2ac36/Untitled.png)

## ✨ 순서 ✨

1. 클라이언트가 연결을 종료하겠다는 FIN을 보낸다 .
2. 서버가 ACK 비트를 클라이언트에게 보내고 자신의 통신이 끝날떄 까지 기다리는데 이 상태를 
    
     TIME_WAIT 상태이다.
    
3. 서버가 통신이 끝났으면 연결이 종료 되었다고 클라이언트에게 FIN을 전송한다.
4. 클라이언트는 확인했다는 메세지를 보낸다.

### ❗(만약) Server에서 FIN을 전송학기 전에 전송한 패킷이 Routing 지연이나 패킷 유실로 인한 재전송 등으로 인해 FIN 패킷보다 늦게 도착하는 상황이 온다면 ??

- client는 세션을 종료시킨 후 뒤늦게 도착하는 패킷이 있다면 패킷은 drop되고 패킷  데이터 유실. 이러한 현상을 대비하여 client는 server로부터 fin을 수신하더라도 일정시간(디폴트 = 240초 ) 동안 세션을 남겨놓고 잉여 패킷을 기다리는 과정을 거친다. 이것이 TIME_WAIT