---
title: "주요 프로토콜"
source: "수업_자료_주요_프로토콜.pdf"
source_format: "슬라이드 이미지(JPEG) ZIP — 확장자만 .pdf"
extraction: "tesseract OCR (kor+eng), 슬라이드별 JPEG 추출"
extracted_at: "2026-05-28"
slides: 47
---

# 주요 프로토콜

> 이 문서는 슬라이드 이미지에서 OCR로 추출한 원본 텍스트입니다. OCR 특성상 일부 오탈자가 있을 수 있습니다.

## 슬라이드 1

_(텍스트 없음 / 이미지 위주 슬라이드)_

## 슬라이드 2

|
JH

자

01 IP, DNS, DHCP

주요 프로토콜이

무엇인지 알아봅니다.
02 TCP/UDP
03 FTP
04 SMTP
05 SSH

06 SSL/TLS

## 슬라이드 3

01
IP, DNS, DHCP

## 슬라이드 4

01 IP, DNS, DHCP

© |P(Internet Protocol)

인터넷 BS EX (Internet Protocol) 2| 약자로

네트워크에서 어떤 정보를 수신하고 송신하는 통신에 대한 규약

## 슬라이드 5

01 IP, DNS, DHCP

OrPsa

비신뢰성                                              비연결형
데이터가 송신지까지                            70『프로토콜과 다르게
정확하게 전달되도록 보장하지는 않음             연결설정 과정 없이 데이터를 전송함

(이 과정은 전송계층에서 일어남)

주소 지정(1『ㅁ)                                  경로 설정(라우팅)
각 기기 장치가 식별될 수 있도록 하는 역할               [『주소를 통하여
IPEAS 통해 라우팅의 경로 설정도                    라우팅의 경로 설정도 가능함

가능하게 됨

## 슬라이드 6

01 IP, DNS, DHCP

© DNS(Domain Name System)

DNS(Domain Name System) = 인터넷 전화번호부와 같음

클라이언트는 도메인 이름을 통해 온라인으로 정보에 액세스가 가능함

https://rsec. kr/2p=506

## 슬라이드 7

01 IP, DNS, DHCP

© DNS 조회 단계

때 2 NS

웹 브라우저에 도메인 이름으로 요청
DNS 서버에서 TLD 서버에 IP 주소 요청
TLD 서버에서 IP FAS 응답
DNS 서버에서 IP FAS 응답

>

## 슬라이드 8

01 IP, DNS, DHCP

© DNS 질의 방식

재귀적 질의
Local DNS 서버에서 Root DNS 서버에 요청을 보내고 그 후 하향식 접근으로 최상위 서버에서

식
밑 쪽으로 |『주소를 검색해 재귀적으로 반환해주는 방식

반복적 질의
Local DNS 서버가 각각의 최상의 서버부터 밑의 서버까지 하나씩 요청

흐 은담: HI
|

=

milo
rr
뚜

>

## 슬라이드 9

01 IP, DNS, DHCP

© DHCP(Dynamic Host Configuration Protocol)

4 4
ea ea

IP FAS} 게이트웨이 또는 네임서버 FAC 정보를 자동으로 할당해주는 프로토콜

히ㄷ
Al
Hale aanaaaa

## 슬라이드 10

01 IP, DNS, DHCP

© DHCP 할당 종류
DHCP 서버의 관리자가 수동으로 개별 장비별(중요 SAL ACH 등)로 고정 설정

수동 할당
(Manual Allocation)
IP 주소의 영구적 독점 사용

자동 할당
(Automatic Allocation)
제한된 수량의 IP 주소 재사용, 한시적 APS (leased period), AS 재활용

동적 할당
(Dynamic Allocation)

## 슬라이드 11

01 IP, DNS, DHCP

© DHCP 동작원리

DHCP Oiscover DHCP AM UHR? HES. Bt BRBUC,
| MASE RIEIPSM BRE OIE. pyicp offer
Dace request |ilisier=s=s=a eae
sets aes se nce ack

+

## 슬라이드 12

02
TCP/UDP

## 슬라이드 13

02 TCP/UDP

© TCP Handshake

연결할래? ZHSILI2(SYIN)
Es
50000 [0 -- |]
=
을 SBoKHACK)

연결하고자 하는 두 장치 간의 논리적 ASS 성립하기 위해 사용

ol
0
[요
ny
이
2
뜨
i

## 슬라이드 14

02 TCP/UDP

© 3 Way Handshake

TCP 연결을 성립하기 위해 3개의 TCP 패킷을 교환하는 통신방식

## 슬라이드 15

02 TCP/UDP

© 4 Way Handshake

## 슬라이드 16

02 TCP/UDP

© TCP(Transmission Control Protocol)

trust

컴퓨터가 다른 컴퓨터와 신뢰성 있는 데이터 SAS 하7

## 슬라이드 17

02 TCP/UDP

© TCP 특징                                                                   / 용어해설
=                                                                                        연결형 방식
: 연결형 방식                                                                     ass
송신자:     }가 서로 연결이
» ㅎ를 및 호존                                                              EE:     !한 후 데이터를
흐름 및 혼잡 제어                                            되었는
: 높은 신뢰성 보장
전이중 방식
ㆍ 3-way handshaking 과정을 통해 AAS 설정하고,                          (Full-Duplex)
=                  Segre                                                  동시에 양방향 전송이 가능한
4-way handshaking 과정을 통해 ABS 해제함                              방식.

40『보다 느린 속도
44 0|Z(Full-Duplex) 2} BHA (Point to Point) 방식

## 슬라이드 18

02 TCP/UDP

© UDP(User Datagram Protocol)

컴퓨터가 다른 컴퓨터와 빠르게 데이터 SNS 하기

## 슬라이드 19

02 TCP/UDP

© UDP 54

ㆍ 비연결형 방스

=

: 신뢰성이 낮음
ㆍ TCPSC} a 빠름
» 정보의 신호절차를 거치지

UDP 헤더의 CheckSum 필

ba

poli

/ 용어 해설

비연결형 방식

송신자와 수신자가 서로 ABO!
되었는지 확인한 후 데이터를
교환하는 방식.

## 슬라이드 20

02 TCP/UDP

© TCP vs UDP

연결 방식                             ame                              비연결형
전송 순서                           전송 순서 보장                      전송 순서 보장 ×
수신 여부 확인                             이                                     x
통신 방식               11             4:1, 1:N, N:N
신뢰성                                      높다                                       낮다

속도                                느리다                               빠르다

## 슬라이드 21

_(텍스트 없음 / 이미지 위주 슬라이드)_

## 슬라이드 22

03 FTP

© FTP(File Transfer Protocol)

Client PC

## 슬라이드 23

03 FTP

© FIP 동작원리

신호/명령제어

데이터 전송

20번 포트

ㆍ FIP 통신은 107 통신을 하기 때문에 처음에 3 Way Handshaking 과정을 거
ㆍ 네트워크 21번 포트를 통해서 ASS 제어하기 위한 신호를 주고,
네트워크 20번 포트를 통해서 실제 데이터 전송을 함

선송끌 암

## 슬라이드 24

03 FTP

© FTP 진행 방식

클라이언트가 『1『 서버와 ASS 설정하면 로그인 WSS 위해 서버에 명령을 보냄

## 슬라이드 25

03 FTP

© FIP 종류
FIP.                                              ID, PasswordS 인증하고 10 프로토콜을 사용하여 데이터를 송수신
TFTP                                             인증을 하지않고 40기반으로 데이터를 빠르게 송수신, 69번 포트 사용

SFTP                                                         전송구간에 암호화 기법을 사용하여 기밀성 제공

## 슬라이드 26

03 FTP

© 『1? 모드

능동 2 (Active Mode)
ㆍ 서버가 데이터 요청을 승인하는 능동적인 역할을 함

ㆍ 제 3자가 권한이 없는 세션에 액세스하려고 하면 해

} 세션이 차단됨

on

수동 20 (Passive Mode)

ㆍ 서버가 능동적으로 AAS 유지하지 않음

ㆍ 사용자가 데이터 채널과 명령 채널 모두를 설정

ㆍ 서버는 기본적으로 듣기만 할 뿐 다른 장치가 대부분의 작업을 처리하도록 함

## 슬라이드 27

03 FTP

© FIPAS

파일 전송을 관리하면 파일 업로드, 이미지 파일 추가,
릿      =          A
등          수월

월하게 처리할 수 있음

a
때
wu
2
에

## 슬라이드 28

03 FTP

© SFTP(Secure File Transfer Protocol)                                   7.30 해설

시큐어 (SSH)
SFTP

Secure Shell. 장치 간의 보안
통신에 사용되는 네트워크
프로콜

ob
=

SFTP(SSH 파일 전송 프로토콜)란 시큐어 셀(5511) 데이터 AEBS 통해 파일 전

## 슬라이드 29

03 FTP

© SFTP

## 슬라이드 30

0360

© SFTP vs FTP

보안성                                       높음                                                                      낮음
방화벽                                     안정적임                                                                  취약함
포트 번호                 단일 포트 번호                                여러 포트 번호

## 슬라이드 31

SMTP

## 슬라이드 32

04 SMTP

© SMTP(Simple Mail Transfer Protocol)

SMTP

IK

네트워크를 통해 전자우편을 전송하는 프로토콜

## 슬라이드 33

04 SMTP

© SMTP 메일 처리 방식

MX —> MDA

MUA

MSA                  MTA

https://www.joinc.co.kr/w/Site/Network_Programing/Documents/SMTP

## 슬라이드 34

04 SMTP

© POP3

메일 서버에서 이메일을 로컬 PCa 수신받을 수 We client/server HE 프로토콜

## 슬라이드 35

04 SMTP

© IMAP(Internet Messaging Access Protocol)

비연결 상태에서 뛰어난 원격 편지함 접근기능을 제공하고
로컬서버에서 전자우편을 엑세스하기 위한 표준 프로토콜

## 슬라이드 36

04 SMTP

© SMTP vs IMAP vs POP3

1019

SMTP: 이메일 클라이언트에서 이메일 서버로 이메일을 보내는데 사용되는 프로토콜
14402: 수신 서버에서 이메일 메시지를 관

ㆍ POP3: 서버에서 클라이언

리하고 검색하는 프로토콜
트로 이메일을 전송하는 방

o

EH
a

## 슬라이드 37

_(텍스트 없음 / 이미지 위주 슬라이드)_

## 슬라이드 38

05 SSH

© TELNET

TELNET

클라이언트
Lo)

|     서버에서 클라이언트
Lo ==]
Lo ==]
Lo -— |

Ce 7)
TX
디스플레이로 출력 [o-- |
[Oo == |
[o -— |

클라이언트 키보드에서
서버로 입력

원격 접속 서비스로서 특정 사용자가 네트워크를 통해 다른 컴퓨터에 연결하여 그
컴퓨터에서 제공하는 서비스를 받을 수 있도록 하는 인터넷 표준 프로토콜

## 슬라이드 39

05 SSH

© SSH (Secure Shell)

Let’s build from here

원격 호스트에 접속하기 위해 사용되는 보안 프로토콜

## 슬라이드 40

05 SSH

© SSH 특징

데이터 AS

원격 제어

모든 데이터 암호화 보장
트래픽 압축으로 더욱 빠른 전송
22번 포트

Public Key2} Private Key 사용

foli

s
=

/ 용어 해설

Public Key
공개되어도 비교적 안전한 Key.
이 키를 통해 메시지를 전송하기
전 암호화를 함.

Private Key

절대로 외부에 노출되어서는
안되는 Key. 본인의 컴퓨터
내부에 저장하게 되어있음.

## 슬라이드 41

05 SSH

© SSH 동작 원리

_+a}4ClznoFtag 1'YD9uSa8SH7ILeIMXnFijSrJiepxp3MiM       wi8OwKsOUE 57

| FIEzuSTZBeUI1sSZXKACUGML 68qQTBROcmcFEGNY 20KSZMz/KZKC

ee ee

apna Ea aise

0

——

은 -

노즈

으으으                =

ees                  =

0         ae] Eee]

오가

0658    Opsa    (60098   (60255 © OssH.1 (RSA)

Lee oe                93
사용자와 서버는 각각의 키를 보유하고 있으며

연결 상대를 인증하고 안전하게 데이터를

이 키를 이용해

WP PUTTY Key Generator                                                       2
File Key Conversions Help

Key

Buble key for pasting into Opens SH authorized 72190:

‘sehr AMAABSNzaClyeZEAAAABJOMAAQEAZCiy

주고 받:

=

게

됨

## 슬라이드 42

06
SSL/TLS

## 슬라이드 43

06 SSL/TLS

© SSL(Secure Sockets Layer)

SSL

암호화 기반 인터넷 보안 프로토콜

## 슬라이드 44

06 SSL/TLS

© TLS(Transport Layer Security)

TLS

86Ｌ보다 더욱 안전한 버전

## 슬라이드 45

06 SSL/TLS

© SSL vs TLS

웹에서 전송되는 데이터를 암호화

ㆍ SSLE 클라이언트와 서버 간에 핸드셰이크를 통해 인
데이터 무결성을 위해 데이터에 디지털 서명을 하여

데이터가 도착하기 전에 조작된 여부를 확

i

인

pas

08

## 슬라이드 46

06 SSL/TLS

© HTTPS(Hyper Text Transfer Protocol Secure)

7s

HTTP                SSL

데이터 유출을 막기 위한 프로토콜

## 슬라이드 47

06 SSL/TLS

SSL, TLS, HTTPS 정리

Application                                                                                           HTTP
Layer
Handshake              Change                                                                         Application
|          Cipher spec       Alert       Handshake       Data
ayer
SSL/TLS

Record                                        Record Layer
Layer

Transport                                                                                           TCP/IP

Layer
