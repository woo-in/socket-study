# 🔌 TCP Socket Study

전문(TCP/IP) 통신을 처음 공부하는 저장소입니다. HTTP만 써 본 상태에서, [firmbanking-mock](https://github.com/Loan-Repayment-System/firmbanking-mock)의 전문 수신부를 Java 기본 소켓으로 만들 수 있게 되는 것이 목표입니다.

## 📕 교재

- **자바의 정석** — 네트워킹 장의 TCP 소켓 프로그래밍, I/O 장의 `DataInputStream` / `DataOutputStream`
- 막히는 API만: [Oracle Java Tutorial – All About Sockets](https://docs.oracle.com/javase/tutorial/networking/sockets/), Javadoc

## 🧭 HTTP와 다른 점 — 이것만 잡으면 된다

| 주제 | 핵심 |
|---|---|
| TCP는 바이트 흐름 | 보낸 횟수와 받은 횟수가 다르다. 메시지 경계는 애플리케이션이 정한다 |
| 고정길이 전문 | 필드 이름 없이 위치(몇 번째 바이트부터 몇 바이트)로 읽는다. EUC-KR 한글은 2바이트다 |
| 연결과 타임아웃 | 읽기 타임아웃이 나도 상대는 이미 처리했을 수 있다 |

## 🗂️ 구성

```
src/main/java/
├─ book/                 # 자바의 정석 예제를 따라 친 코드
│  ├─ io/                #   DataInputStream / DataOutputStream
│  └─ tcp/               #   ServerSocket / Socket, 멀티스레드 서버
└─ practice/             # 직접 짜는 실습 (각 폴더 README에 목표·완료 조건)
   ├─ echo/              #   1. 에코 서버
   ├─ boundary/          #   2. 경계 문제 재현
   ├─ lengthheader/      #   3. 길이 헤더로 해결
   ├─ fixedlength/       #   4. 고정길이 필드와 EUC-KR
   ├─ timeout/           #   5. 읽기 타임아웃
   └─ multiclient/       #   6. 여러 클라이언트 동시 처리
```

실습은 포트 `9000`을 쓴다. 서버와 클라이언트는 각자 `main`을 두고 IDE에서 따로 실행한다.

## ✅ 진행

### 책

- [ ] 자바의 정석 — I/O 장 `DataInputStream` / `DataOutputStream` → `book/io`
- [ ] 자바의 정석 — TCP와 UDP 비교
- [ ] 자바의 정석 — TCP 소켓 프로그래밍 → `book/tcp`

### 실습

- [ ] 1. [에코 서버](src/main/java/practice/echo/README.md)
- [ ] 2. [경계 문제 재현](src/main/java/practice/boundary/README.md)
- [ ] 3. [길이 헤더로 해결](src/main/java/practice/lengthheader/README.md)
- [ ] 4. [고정길이 필드와 EUC-KR](src/main/java/practice/fixedlength/README.md)
- [ ] 5. [읽기 타임아웃](src/main/java/practice/timeout/README.md)
- [ ] 6. [여러 클라이언트 동시 처리](src/main/java/practice/multiclient/README.md)
