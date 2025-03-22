<h1 align='center'>🧐 WEB-SOCKET 연결 과정에 대해 설명해주세요! </h1>

**`KEY WORD`**: `HTTP 1.1에서만 업그레이드 가능`, `STATE-LESS 에서 STATE-FULL 로`, `HEART-BEAT로 연결 지속!`

<h1 align = 'center'> 🙋🏻‍♂️ 면접 1분 대답 ! </h1>

**WebSocket**은 Http1.1에서만 업그레이드가 가능한 프로토콜로, 기존의 state-less한 http 요청 응답 패턴에서, heart-beat를 활용한 state-full 한 상태로 서버-클라이언트 연결을 변환합니다. 크게 다음의 3가지 과정으로 Web-Socket 연결이 이루어 집니다.

1. 클라이언트가 Header에 Upgrade: Websocket Attribute를 담아 연결을 요청합니다.
2. 서버가 Header에 `Http/1.1 101 Switching Protocol`을 보내, 이제 연결을 state-full한 상태로 지속할 것임을 클라이언트에게 알립니다.
3. 방화벽이나 기타 보안에 의해 연결이 기별없이 끊길 수 있으므로, 서로 heart-beat를 보내며 연결이 살아 있는지 확인합니다.

<h1 align='center'>📝 자세한 설명 (추가 질문 대처하기!) 📝</h1>


![1](https://github.com/user-attachments/assets/ef316854-0cd8-4ba5-b237-82a83c08bcbe)
![2](https://github.com/user-attachments/assets/45efa77d-2bc9-469b-8576-c8788a5b6d91)
![3](https://github.com/user-attachments/assets/2f1fa44f-e7ee-4a59-b303-1442693b1757)
![4](https://github.com/user-attachments/assets/6f540335-8e96-4154-8b2e-1a78c61921f0)



> 추가 설명!

위와 같이 클라이언트에서는 `STOMP.connect(wss://서버 URL)`을 할 것인데요. (편의상 Client에서는 STOMP protocol을 쓰고 있다고 가정하겠습니다.) 하지만 해당 요청은 사실 `HTTP GET` 요청으로 보내지고, 다만 Header에 Upgrade라는 Attribute가 추가될 뿐입니다!

![5](https://github.com/user-attachments/assets/08c1bee5-d72d-45b5-863a-e7c0e080ef17)
![6](https://github.com/user-attachments/assets/d040c39e-4770-4f2c-b015-c89b3ce9ebe5)
![8](https://github.com/user-attachments/assets/8a3fb61b-9d85-4428-875e-b5e9e17e8ab0)
![7](https://github.com/user-attachments/assets/25ce7dc8-2247-4894-a684-cb43f47db7c9)
![9](https://github.com/user-attachments/assets/05f1f292-eaa9-4fe9-9ea4-eb2233de9e73)




이상입니다! 

저희 레포지토리에 ⭐를 넣어두시거나 ` WATCH` 설정을 해두시면, 매일 새로운 CS 면접 대비 질문과 대답으로 찾아뵙겠습니다^^
