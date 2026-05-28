---
title: "인터넷과 HTTP"
source: "수업_자료_인터넷과_HTTP.pdf"
source_format: "슬라이드 이미지(JPEG) ZIP — 확장자만 .pdf"
extraction: "tesseract OCR (kor+eng), 슬라이드별 JPEG 추출"
extracted_at: "2026-05-28"
slides: 55
---

# 인터넷과 HTTP

> 이 문서는 슬라이드 이미지에서 OCR로 추출한 원본 텍스트입니다. OCR 특성상 일부 오탈자가 있을 수 있습니다.

## 슬라이드 1

핵심 YESS

02 Olea} HTTP

## 슬라이드 2

목차

인터넷과 HTTP7

무엇인지 알아봅니다.

01
02
03
04
05
06

TCP/IP
프로토콜
HTTP

상태코드 |

## 슬라이드 3

01
TCP/IP

## 슬라이드 4

01 TCP/IP

© TCP/IP#t?
TCP/IP

목적지

데이터가 정확한 목적지에 도달할

적인 프로토콜로도 사용 가능함

ㆍ 디바이스를 연결하는
을

ㆍ 데이터 패킷

프로토콜의 집합이며 개별적인 프
른위

|치로 전송하여 다른 컴퓨터와 통신할 수 있음

^ 용어 해설

Ate! (compile)

주어진 언어로 작성된 컴퓨터
프로그램을 다른 언어의 동등한
프로그램으로 변환하는
프로세스.

## 슬라이드 5

01 TCP/IP

© TCP
TCP
신뢰성
a =   =
다중화               느  4
데이터 ASS 위한 연결지향 프로토콜
ㆍ 신뢰성 :적극적 수신, 통신 재전송 AAS 사용함
ㆍ 흐름제어 : 송신자가 보낸 데이터의 SS 제어하는 메커니즘을 구현함
ㆍ CBs}: AA 컴퓨터의 응용 프로그램 프로세스 사이에 머리 ¢ 연결이 존재할

## 슬라이드 6

01 TCP/IP

© IP

## 슬라이드 7

01 TCP/IP

© OSI 7AlIS vs TCP/IP 모델

TAS

응용 계층
6계층                         표현 계층                            4계층                         응용 계층
5계층                        세션 계층
4계층                          전송 계층                             3계층                          전송 계층
3계층                          네트워크 계층                             2계층                            인터넷 계층
2계층              데이터링크 계층

1계층                        네트워크 엑세스 계층

1계층                             물리 계층

700/1『 모델은 네트워크 통신이 일어나는 과정을 4단계로 나눈 것
(OSI 4계층이라고도 부름

https://velog.io/@jehjong/7H 4 At- 2 E} 4#-TCPIP-4AS

## 슬라이드 8

01 TCP/IP

© 응용 AlB (Application Layer)

데이터 단위

역할

DATA/Message

## 슬라이드 9

01 TCP/IP

© 전송 AlZ (Transport Layer)

데이터 단위

Segment
z                    통신 노드 간의 연결 제어 및
“                                        자료 송수신을 담당
he                                              전송 계층
전송 주소

## 슬라이드 10

01 TCP/IP

© 인터넷 73 (Internet Layer)

데이터 단위                                  Packet

네트워크상 최종목적지까지

역할
정확하게 연결되도록 연결성을 제공
종류                               네트워크 계층

## 슬라이드 11

01 TCP/IP

© 네트워크 엑세스 AlZB (Network Access Layer)

데이터 단위                                            Frame

물리적으로 데이터가 네트워크를 통해
어떻게 전송되는지를 정의

역할

종류                    물리 계층, 데이터 링크 계층

전송 주소                                                  MAC #48

## 슬라이드 12

01 TCP/IP

© PIE} Hl (Internet)

20

버0

Tol
=

dl

터들

전 세계

서로 동시에 참여

00

SA
주고 받을 수 있

Al 제약을 받지 않고 메세지를

언제든

이미지, 음성, 동영상

했지만 현재에는

—
=4

텍스트로만 통신이 가

초기에는 턱

## 슬라이드 13

01 TCP/IP

© 인트라넷과 엑스트라넷

인트라넷
+ '내부의(1003)'라는 의미의 단어와 네트워크의 줄임말 Neto] 결

ㆍ 해당 회사에 속

할 있는
구축하는 가장 큰 이유는 보안 때문임

때
ra
ot
오

속한 직원만 접근  그할   는 사설망

Tow

엑스트라넷
ㆍ '바깥의(68)'라는 의미의 단어와 네트워크의 줄임말 Neto] 결합된 용어
ㆍ 인트라넷과 달리 외부 협력사 또는 고객들도 접속 가능함

ㆍ 고객에게 가용성 있는 서비스를 제공하고, 협력사와 원활하게 업무를 진행

## 슬라이드 14

01 TCP/IP

© 인터넷/엑스트라넷/인트라넷

접근성                      공개, 제한×                   한정적 공개                  비공개, 제한적
사용자                            제한×                      aga 관련 그름                  허용된 사용자

정보형태                      일반적, 대중적           그룹들 사이에 응용되는 정보       개인적, 통제된 정보

## 슬라이드 15

프로토콜

## 슬라이드 16

02 프로토콜

© 프로토콜(『6『010001)

6
io!
RO

00
ulo

100
100

00
ulo

ㆍ 신호 처리법, 오류처리, 암호, 인증, 주소

조오
su

= 것이

프로토콜을 통일시키

"서는

we 퀴히

신을 우

한통

## 슬라이드 17

02 프로토콜

© 네트워크 아키텍처 (Network Architecture)

(복잡한) 시스템                               (단순한) 아키텍처

복잡한 네트워크 시스템을 프로토콜의 조합으로 단순화한 것
(프로토콜의 집합)

## 슬라이드 18

02 프로토콜

©

See                 전송하고자 하는 데이터의 형식, 부호화, 신호 레벨 등을 규정
의미            효율적이고 정확한 정보 전송을 위한   정보를 규정

(Semantics)               SENN BE 정보 ESE HEN ERE 규정
시간                                     통신 속도, 순서 제어 등을 규정

(Timing)

## 슬라이드 19

02 프로토콜

© 프로토콜의 기능

기능
단편화/재합성
캡슬화

연결/흐름/오류 제어

순서 결정

동기화/다중화

역할
데이터 블록을 나누고 합쳐서 전송

프로토콜에 필요한 데이터 정보를 부착

요한 연결/흐름/오류를 개설조정-종결

데이터 ASO] 필요
데이터 단위 순서대로 수신 측에 전달

소를 명기하여 데이터를 전달

상태를 일치시키는 기능/통신로를 나누어 동시에 사용할 수 있도록 하는 가능

## 슬라이드 20

02 프로토콜

© 캡숄화(0305413100) & 역캡

#5} (Decapsulation)

에서 통신 프로토콜 정보를 데이터에 추가
통신 프로토콜 정보를 데이터에서 제거

## 슬라이드 21

02 프로토콜

© 051 7계층과 프로토콜

계층                                                                프로토콜
$2 (Application)                                                   HTTP, SMTP, FTP, Telnet
EH (Presentation)                                             ASCII, MPEG, JPEG, MIDI
세션 (Session)                                                 NetBIOS, SAP, SDP, NWLink
4 (Transport)                                                     TCP, UDP, SPX
네트워크 (Network)                                                         IP, IPX
데이터 35 (Data Link)                                         Ethernet, Token Ring, FDDI, AppleTalk

물리 (Physical)                                                             없음

## 슬라이드 22

HTTP

## 슬라이드 23

03 HTTP

© HTTP(Hyper Text Transfer Protocol)

HTTP.
REQUEST

HTTP
Response

를

ㆍ 전통적인 클라이언트-서버 모델을 따름
a       로토콜이며, 서버가 어떠한 상태나 데이터를 유지하지 LSS 의미함

10
oz
본

## 슬라이드 24

03 HTTP

© HTTP 구조
Start Line                                                     요청라인/상태라인
Header                                                                       헤더는 생략 가능
Empty Line                                                          공백라인

Message Body                                                               메시지 본문

## 슬라이드 25

03 HTTP

© HTTP 헤더

HTTP HEADER

클라이언트와 서버가 요청 또는 응답으로
부가적인 정보를 전송할 수 있게 해줌

로                                    est              Entity
pesca            non   a          Header:

요청, 응답에 대한 정보를 포함
-갑 쌍으로 설정되며 :로 구분됨

## 슬라이드 26

03 HTTP

© HTTP 메서드
GET                                                                자료를 조회할 때 사용
POST                                                                 자료를 SSE 때사용
PUT                                                      자료의 수정을 요청할 때 사용

Delete                                                    자료의 AMS 요청할 때 사용

## 슬라이드 27

03 HTTP
© CRUD
Cc                     R                      U
Create               Read                Update           Delete

대부분의 컴퓨터 소프트웨어가 가지는 기본적인 데이터 처리 기능

## 슬라이드 28

03 HTTP

© Request & Response
Request                          Response

이     oO -— |
000000000002                         jo -— |

HTTP 메시지는 서버와 클라이언트 간에

데이터를 교환하는 방법

## 슬라이드 29

_(텍스트 없음 / 이미지 위주 슬라이드)_

## 슬라이드 30

04 상태코드 |

© 상태코드(5【3146 Code)

U/relicex/)     고    로그인
ㅁ×%교육은 엘리스        요청 메서드: GET

국내 기업 임직원
.30만 명의 선택

상태 코드: @ 200

클라이언트의 요청에 대한 상태에 대한 서버의 응답

https://elice.io/

## 슬라이드 31

04 상태코드 |

© 1××상태 코드
Information : 100번대(정보 응답)

Continue

100       - MH7t request 헤더는 받았고, 클라이언트가 request 바디 부분을 보내고 있는 상태
Switching Protocol

이        - 요청자가 서버에게 Switching ProtocolS 묻는 상태

102       Processing
- 요청자에 의해 MH 7} LAS 수신하였으며 이를 처리했지만, 응답이 없는 상태

103      Checkpoint

- 중단된 『나과 Post LAS 재개할 목적으로 되찾을 수 WE requestS 사용하는 상태

YA

Ixx (정보): LAS 받았으며 프로세스를 계속한다

## 슬라이드 32

04 상태코드 |

© 2xx SE 코드
Successful : 200번대(성공 응답)

200

201

202

203

204

OK

- 에러 없이 ASO] 성공된 상태

Created

—request7} 되었고, 새로운 자원이 만들어진 상태

Accepted

- 서버가 requests 전송받았으나 현재 완전하게 처리되진 않은 상태
Non-Authoritative Information

- 서버가 클라이언트 요구 중 일부만 전송한 상태

No Content

-서버가 클라이언트 QPS 처리했으나 전송할 데이터가 없는 상태

## 슬라이드 33

04 상태코드

© 2×%×상태 코드

Successful : 200번대(성공 응답)

코트

205

206

207

208

226

설명

Reset Content

~ No 000【60【상태라서 요청자의 document view2| resetO| 필요한 상태

Partial Content

- 클라이언트의 header 범위 문제로 MH 7} 자원 일부만 전달받은 상태

Multi-Status

- 멀티-상태 응답은 다수의 리소스가 여러 개의 상태 코드인 상황이 적절한 경우에 해당하는
정보를 서비스에 전달한 상태

Multi-Status

- 멀티-상태 응답 0&\에서 AtS, propstat(property?t status2] 합성어) 응답 속성으로 동일
컬렉션으로 바인드된 복수의 내부 WHS 반복적으로 열거하는 AS 피하려고 사용하는 상태

IM Used

-서버가 GET 요청에 대한 리소스를 처리했으며, 응답이 하나 또는 그 이상의 인스턴스 조작이
현재 인스턴스에 적용이 되었음을 알리는 상태

## 슬라이드 34

04 상태코드 |

© 3xx SE 코드

Redirection : 300번대(리다이렉션 응답)

Multiple Choices

300
- 최대 다섯 개의 링크를 골라서 이동할 수 있는 상태
301   Moved Permanently
—E—E ea                       3xx (ZITO): 요청 완료를 위해 주가 작업 조치가 필요하다
302   『0400
- QUE 페이지가 일시적으로 새 URLS 옮겨진 상태
See Other
303                                   .
- 요청된 페이지는 CHE URLOIA 찾을 수 있는 상태
Not Modified
304

- 마지막 요청 이후 수정되지 않은 상태

## 슬라이드 35

04 상태코드 |

© 3xx SE 코드

Redirection : 300번대(리다이렉션 응답)

305       Use Proxy
~ location fieldO| proxy2] URLS 사용하는 상태
Switch Pro:
306                    때
- 사용하지 않는 FE (Unused)
307      Temporary Redirect 302 Found HTTP SG 코드와 동일한 의미가 있으며, 사용자
에이전트가 반드시 사용된 HTTP 메소드를 변경하지 말아야 하는 점만 다른 상태
308       Permanent Redirect 301 Moved Permanently HTTP SB 코드와 동일한 의미가 있으며,

사용자 에이전트가 반드시 HTTP 메소드를 변경하지 말아야 하는 점만 다른 상태

35%(리다이렉션): 요정 완료를 위해 추가 작업 조치가 필요하다

## 슬라이드 36

_(텍스트 없음 / 이미지 위주 슬라이드)_

## 슬라이드 37

05 상태코드 ||

© 4xx aE 코드

Client Error : 400번대(클라이언트 에러 응답)

Bad Request

400

- LAA SO] 문법적인 오류가 있어서 서버가 이해할 수 없는 상태

Unauthorized
401

- 해당 요청에 대한 권한이 없는 상태                                                            no) a

4x (클라이언트 오류): 요청의 SHO]

402 Payment Required                                                                             잘못되었거나 SAS 처리할 수 없다
403      Forbidden

-금지된 요청을 허가하지 않는 상태

Not Found
404

- 요청한 페이지를 찾을 수 없는 상태

## 슬라이드 38

05 상태코드 ||

© 4xx SE 코드
Client Error : 400번대(클라이언트 에러 응답)

405      Method Not Allowed
- 「604651에 명시된 요청 Method7t 제공되지 않은 상태

406     Not Acceptable                                                          _
— requestO|A] accept headerO| not acceptable2| 내용을 가진 AAS 요청한 상태
rox Authentication Required                     axx (클라이언트 오류): 요청의 문법이
uthentication Require                                                                              =o 이이
407 “real 서버에게 해당 요정이 수행되도록 인증받아야 하는 상태                             잘못되었거나 요청을 처리할 수 없다

SUS

Request Timeout
408 ~ SB 대기 시간이 지난 상태

409      Conflict
- request SSE 인해서 요청이 완료되지 않은 상태

## 슬라이드 39

05 상태코드 ||

© 4xx aE 코드

Client Error : 400번대(클라이언트 에러 응답)

410

411

412

413

414

Gone
- 요청 페이지는 더 이상 사용할 수 없는 상태

Length Required
- Content-Length 부분이 빠져서 요청을 허가하지 않은 상태

Precondition Failed
~ request 헤더 필드에 선결 조건에 대한 값이 서버에서 3156가 나온 경우

Request entity too large
- 요청 엔티티를 서버가 처리하기에 너무 2 상태

Request-URI Too Long
- 요청 URI7E 너무 2! 상태

4xx (클라이언트 오류): 요청의 문법이
잘못되었거나 LAS 처리할 수 없다

## 슬라이드 40

05 상태코드 ||

© 4xx SEH 코드
Client Error : 400번대(클라이언트 에러 응답)

Axx

415

416

417

421

Unsupported Media Type
- 지원하지 않는 미디어 타입을 요청한 상태

Requested Range Not Satisfiable
- 클라이언트가 파일 AHS 요청했을 때 서버가 지원하지 않는 상태

Expectation Failed                                     _
- Expect request-header HE9| 27S 서버가 충족시킬 수 없는 상태

Misdirected Request
- 서버로 유도된 요청 SES 서버에서 생성할 수 없는 상태

(클라이언트 오류): 요청의 문법이 잘못되었거나 요청을 처리할 수 없다

## 슬라이드 41

05 상태코드 ||

© 4xx SE 코드
Client Error : 400번대(클라이언트 에러 응답)

422      Unprocessable Entity
- 요청은 잘 전달 됐지만, 문법 오류가 난 상태

423      Locked
- 요청한 리소스에 접근하는 것이 잠겨있는 상태

424      Failed Dependency
- 이전의 요청이 실패한 상태에서 지금의 LAS 실패한 상태

Upgrade Required

426  -클라이언트에서 보낸 요청의 프로토콜이 맞지 않아 현재 서버에서 처리할 수 없으나,
클라이언트가 다른 프로토콜로 업그레이드한다면 처리의 가능성이 있는 상태

4x (클라이언트 오류): 요청의 문법이 잘못되었거나 요청을 처리할 수 없다

## 슬라이드 42

05 상태코드 ||

© 4xx SEH 코드
Client Error : 400번대(클라이언트 에러 응답)

428

429

431

451

Precondition Required
- 요청이 조건부여야 하는 상태

Too Many Requests
~ 사용자가 지정된 시간에 너무 많은 요청을 보낸 상태

Request Header Fields Too Large
- 요청한 헤드 필드가 너무 커서 서버에서 처리하지 않는 상태

Unavailable For Legal Reasons
- 정부에 의해 ASE A 페이지와 같은 불법적인 AAAS 요청하여 거부된 상태

4x (클라이언트 오류): 요청의 문법이 잘못되었거나 요청을 처리할 수 없다

## 슬라이드 43

05 상태코드 II

© 5xx aE 코드
Server Error : 500번대(서버 에러 응답)

Internal Server Error

500         - 일반적인 서버 에러 메세지로 요청 사항을 이행할 수 없는 상태
501          Not Implemented

- MH} 해당 요청 메소드를 인식 못 하거나, 이행할 능력이 없는 상태
502         Bad Gateway                                         .

- 게이트웨이나 프록시의 상태가 나쁘거나 과부하인 상태

Service Unavailable
503     - 일시적인 과부하나 서비스 중단 상태                                              a
(임시 조건에 사용되어야 하며, Retry-After: HTTP 헤더는 가능하면 서비스를 복구하기 전 예상 시간을 포함해야 함)

xx (|| 오류): 서버가 명백히 유효한 요청에 대해 SSS 실패했다

## 슬라이드 44

05 상태코드 II

© 5xx aE 코드
Server Error : 500번대(서버 에러 응답)

504        Gateway Timeout
- 과부하 등의 이유로 게이트웨이나 프록시의 한계 대기 시간이 지난 상태

505         HTTP Version Not Supported
~requestd|A| 사용한 111『 프로토콜을 서버가 지원하지 않는 상태

506      Variant Also Negotiates
~ 서버 내부 구성에 오류가 있어 반환되는 값에 콘텐츠 협상이 순환 참조로 이루어져 있는 상태

Insufficient Storage
507       ~ At 내부에 구성 오류가 있어 선택된 리소스는 투명한 콘텐츠 협상에 참여하도록 구성되므로 협상 과정에서

적절한 끝점이 아님을 알려주는 상태

xx (|| 오류): 서버가 명백히 유효한 요청에 대해 SSS 실패했다

## 슬라이드 45

05 상태코드 ||

© 5xx aE 코드
Server Error : 500번대(서버 에러 응답)

508     Loop Detected
- 서버가 요청을 처리하는 동안 무한 루프를 감지한 상태

510    Not Extended
- 서버가 요청을 처리할 때 요청에 대한 추가 확장이 필요한 상태

511       Network Authentication Required
- 클라이언트의 접근을 위한 네트워크 인증이 필요한 상태

xx (| 오류): 서버가 명백히 유효한 요청에 Hof SSS 실패했다

## 슬라이드 46

CORS

## 슬라이드 47

06 CORS

© CORS(Cross-Origin Resource Sharing)

HOVE! Ns!                                                                  apa EE 되는지 ROLE

## 슬라이드 48

06 CORS

© SOP(Same-Origin Policy)

HONEA SUE!                                                                              ‘SUM SENSI! 들게!

## 슬라이드 49

06 CORS
© SOP(Same-Origin Policy)

https://www.example.com:182/category/blog/index.html

프로토콜 서브 도메인 도메인 및도메인확장자 포트          서브 디렉토리            웹 페이지

Scheme(Protocol), Host(Domain), Port 로 구성

## 슬라이드 50

06 CORS

© Origin Example

<!--1. <img>, <video>, <script>, <link> 태그 -> 7/2422 Cross-Origin 정책을 지원함 >
<link crossorigin rel="stylesheet” href=”...” />

<link crossorigin rel=” preload” as=”font” href=”...” />

<script corssorigin src=”...”></script>

<img crossorigin src=”...” />

웹 브라우저는 HTTP 요청에 대해서 어떤 LAS 하느냐에 따라

Cc      =
각기 다른 특징을 가지고 있습니다.

## 슬라이드 51

06 CORS

© Cors Request 33
Simple Request

Content-type 헤더는 다음의 값들만 허용됨

+ text/plain
* multipart/form-data
ㆍ application/x-www-form-urlencoded

get, post, head 메서드 중 하나 사용함
PreflightedS 제외한 요청

Preflighted Request

먼저 0110445 메서드를 통해 다른 도메인의 리소스로 HTTP 요청을 보내 전송하기에

안전한지 확인함

적기

cross-origin 2A2 유저 데이터에 영향을 줄 수 있기 때문에 미리 전송

## 슬라이드 52

06 CORS

© Same Origin vs Same Site

Se AEE a 2

esos oauan ae

위와 같

NAVER 웹툰

^: HE 베스트도전 . 도전만화
| '뻐              ‘4

늘의

투

마이페이지

1월 20일토요일

= err O:=.

H (Origin) St? 같은 AtO| E (Site) Lt?

## 슬라이드 53

06 CORS

© Same Origin

https://www.angel.com:448
https://example.com:448
https://login.example.com:448
http://www.example.com:448
https://www.example.com:70
https://www.example.com:448

https://www.example.com

cross-origin: domains 불일치
cross-origin: subdomains 불일치
cross-origin: subdomains 불일치
cross-origin: schemes 불일치
cross-origin: RE 번호 불일치
same-origin: 정확한 일치

same-origin: 암시적 포트 번호(448) 일치

출처(20010)의 도메인, 호스트, 포트 번호가 같을 경우

할수 있음

출처라 말

때

## 슬라이드 54

06 CORS

© Same Site

cross-site: domains 불일치

https://www.angel.com:448
https://login.example.com:448
https://Awww.example.com:448
https://www.example.com:70
https://www.example.com:448

https://www.example.com

same-site: C+= subdomains S#&aS
same-site: C+ schemes? 상관없음
same-site: 다른 포트 번호는 상관없음

same-site: 정확한 일치

same-site: 포트 번호 상관없음

사이트라고 할 수 있음

## 슬라이드 55

06 CORS

© Same Origin vs Same Site 구별

https://www.angel.com:448
https://example.com:448
https://login.example.com:448

http://www.example.com:448

https://www.example.com:70

https://www.example.com:448

https://Awww.example.com

cross-origin: domains 불일치

cross-origin: subdomains 불일치

cross-origin: subdomains 불일치

cross-origin: schemes 불일치
cross-origin: 포트 번호 불일치
same-origin: 정확한 일치

same-origin: 암시적 포트 HS (448)
일치

https://www.angel.com:448
https://login.example.com:448
https://www.example.com:448

https://Awww.example.com:70

https://www.example.com:448

https://www.example.com

cross-site: domains 불일치

same-site: C+ subdomains
상관없음

same-site: 다른 50160165은
상관없음

same-site: 다른 포트 번호는
상관없음

same-site: 정확한 일치

same-site: 포트 번호 상관없음
