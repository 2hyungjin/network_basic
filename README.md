# 네트워크

## 컴퓨터 네트워크

**두 대 이상의 컴퓨터가 연결되어 있는 것**을 컴퓨터 네트워크라고 하고, 컴퓨터 간에 필요한 데이터를 서로 주고받을 수 있습니다.

전 세계의 크고 작은 네트워크를 연결하는 거대한 네트워크를 **인터넷** 이라고 합니다.

#### 패킷(packet)

컴퓨터 간에 데이터를 주고받을 때 **네트워크를 통해 전송되는 데이터의 작은 조각**을 패킷이라고 합니다.

큰 데이터를 그대로 보내면 네트워크의 대역폭을 많이 차지(점유)하기 때문에 패킷을 사용합니다.

#### 디지털 데이터(digital data)

컴퓨터는 이진수(0과 1)을 사용하며 그 0과 1의 집합을 디지털 데이터라고 합니다.

**비트는 0과 1의 정보를 나타내는 최소 단위**입니다.

**바이트는 8비트를 나타내는 단위**이며 컴퓨터는 주로 바이트 단위로 데이터를 읽고 씁니다.

문자를 디지털 데이터로 변환하기 위해서는 문자 코드를 사용하며 해당 문자에 대응하는 숫자로 변환시킵니다. (ex : ASCII 코드...)

#### LAN(Local Area Network), WAN(Wide Area Network)

**LAN(랜)은 건물 안이나 특정 지역을 범위로 하는 네트워크**입니다. 연결하는 거리가 짧기 때문에 **속도가 빠르고 오류 발생 확률이 적습니다.**

**WAN(왠)은 ISP(인터넷 서비스 제공자)가 제공하는 서비스를 사용하여 구축된 네트워크**입니다. 랜과 랜을 연결하는 것이며 거리가 멀기 때문에 랜에 비해 **속도가 느리고 오류 발생 확률이 높습니다.**

ISP : 인터넷 상용 서비스 사업을 하는 사업자 (KT, U+, SK브로드밴드와 같은 통신 회사들)

#### 가정에서의 네트워크

가정에서 네트워크를 사용하기 위해서는 

1. ISP의 인터넷을 WAN을 통해 인터넷 공유기에 전달합니다.
2. 인터넷 공유기(무선 랜 공유기)를 중심으로 내부 인터넷망(사설망)을 구성합니다.
3. LAN 케이블을 이용한 유선 랜과 케이블이 필요 없는 무선 랜으로 다양한 기기를 연결합니다.

#### 소규모 회사의 네트워크

회사의 네트워크 구성은 가정에서의 네트워크와 다른데 간단히 말하자면 **DMZ라는 외부에 공개하는 네트워크가 있다는 점**입니다.

회사에서는 웹 서버, 메일 서버 등 외부 사용자에게 공개하기 위한 네트워크가 있으며 이를 DMZ라고 합니다.

회사에서는 서버를 사내 혹은 데이터 센터에 두거나(온프레미스) 클라우드에 두고 운영합니다.

## 프로토콜

**컴퓨터 간의 원활한 통신을 위해 지키기로한 규약을 프로토콜**이라고 합니다.

#### OSI 모델 & TCP/IP 모델

**OSI 모델은 ISO(국제표준화기구)에서 정한 네트워크의 기본이 되는 모델**입니다.

**물리 계층, 데이터 링크 계층, 네트워크 계층, 전송 계층, 세션 계층, 표현 계층, 응용 계층**의 일곱 개의 계층으로 구성됩니다.

송신할 때에는 응용 계층부터 물리 계층까지 수신할 때에는 물리 계층부터 응용 계층까지의 순서대로 데이터를 전달합니다.

**TCP/IP 모델은 4계층으로 이루어진 네트워크 모델**입니다.

**네트워크 접속 계층, 인터넷 계층, 전송 계층, 응용 계층** 네 개의 계층으로 구성됩니다.

OSI 모델의 물리 계층, 데이터 링크 계층이 TCP/IP 모델의 네트워크 접속 계층으로, 네트워크 계층이 인터넷 계층으로, 세션, 표현, 응용 계층이 응용 계층으로 이루어져 있습니다.

#### 캡슐화와 역캡슐화

**데이터를 전송할 때 전송에 필요한 정보를 붙여서 보내는데 이 정보를 헤더**라고 합니다. (헤더에는 수신 측의 정보도 포함되어 있습니다.)

**헤더를 붙이는 과정을 캡슐화, 제거하는 과정을 역캡슐화**라고 합니다.

**데이터를 전송할 때, OSI 7계층에서 각 계층에 해당하는 헤더를 붙이며(캡슐화) 데이터 링크층에서는 데이터의 마지막에 추가하는 정보인 트레일러를 붙입니다.**

이렇게 만들어진 데이터는 전기신호로 바뀌어 수신 측에 도착하고 **수신 측에서는 해당 계층의 헤더를 제거(역캡슐화)하며 상위 계층으로 전달**합니다.

## 물리 계층

**물리 계층은 컴퓨터와 네트워크 장비를 연결하고 전기 신호로 변환하는 계층**입니다.

데이터를 통신할 때에는

1. 비트열 데이터를 전기 신호로 변환
2. 네트워크를 통해 수신 측에 도착
3. 수신 측에서 전기 신호를 비트열 데이터로 복원

의 과정을 거칩니다.

**비트열 데이터는 컴퓨터의 랜카드를 통해 전기신호로 변환**됩니다.

#### 트위스티드 페어 케이블(렌 케이블)

전송 매체(데이터가 흐르는 물질적인 선로)에는 유선과 무선으로 나뉘어집니다.

유선에는 트위스트 페어 케이블, 광 케이블 등이 있고, 무선에는 라디오파, 마이크로파, 적외선 등이 있습니다.

**트위스티드 페어 케이블은 일반적으로 랜 케이블이라고 부르며 UTP(Unshield Twisted Pair) 케이블과 STP(Shield Twisted Pare) 케이블**이 있습니다. **렌 케이블 양쪽 끝에는 RJ-45라고 부르는 커넥터가 붙어있으며 이 커넥터를 사용해 네트워크 기기에 연결**할 수 있습니다.

**STP 케이블은 두 개씩 꼬아 만든 선을 실드(금속 호일이나 금속의 매듭같은 것으로 노이즈를 막는 역할을 함)로 보호한 케이블**입니다. **노이즈(케이블에 전기 신호가 흐를 때 발생하는 것이며 전기 신호의 형태가 왜곡됨)의 영향을 매우 적게** 받지만 비싸서 보편적이지는 않습니다.

**UTP 케이블은 두 개씩 꼬아 만든 네 쌍의 전선**으로 **실드로 보호 받지 않는 케이블**입니다. **노이즈의 영향을 받기 쉽지만 저렴**하기에 보편적으로 사용됩니다.

렌 케이블에는 다이렉트 케이블과 크로스 케이블이 있습니다. 두 케이블 모두 1, 2, 3, 6번 구리선을 사용하지만 연결 방식에 따른 차이가 있습니다. 

**다이렉트 케이블은 구리 선 여덟 개를 같은 순서로 연결한 케이블로 컴퓨터와 스위치를 연결할 때 사용**합니다.

**크로스 케이블은 구리 선 여덟 개 중 한쪽 커넥터의 1,2번에 연결되는 구리 선을 다른 쪽의 3번 6번에 연결한 케이블이며 컴퓨터 간에 직접 연결할 때 사용**합니다.

#### 리피터와 허브

리피터와 허브는 물리 계층에서 동작하는 네트워크 장비입니다.

**리피터는 전기 신호를 정형하고 증폭하는 기능**을 합니다. 멀리 있는 상대와 통신할 수 있도록 파형을 정상으로 만들어 주는 역할을 하지만 요즘에는 다른 네트워크 장비가 리피터 기능을 지원하기에 따로 사용할 필요는 없습니다.

**허브는 리피터와 마찬가지로 전기 신호를 정형하고 증폭하는 기능을 하며 포트가 여러 개 있어서 컴퓨터 여러 대를 서로 연결하는 장치**로써 쓰입니다. 

**특정 포트로부터 데이터를 받으면 연결된 모든 포트에게 전송하기 때문에 더미 허브**라고 불리기도 합니다.

## 데이터 링크 계층

**데이터 링크 계층은 네트워크 장비 간에 신호를 주고받는 규칙을 정하는 계층**입니다.

랜에서 데이터를 정상적으로 주고받기 위해 필요한 계층이며 그 규칙들 중 일반적으로 많이 사용되는 규칙이 **이더넷(Ethernet)**입니다.

#### 이더넷

이더넷은 허브와 같은 장비에 연결된 컴퓨터와 데이터를 주고 받을 때 사용합니다.

허브는 모든 포트에 데이터를 전송하기 때문에 이를 방지하기 위해 보내려는 데이터에 목적지 정보를 추가하여 목적지 이외의 컴퓨터는 데이터를 받더라도 무시하게 합니다.

여러 컴퓨터가 데이터를 전송해도 충돌이 일어나지 않도록 하기 위해서 데이터를 보내는 시점을 늦추는 **CSMA/CD** 방법을 사용합니다.

CSMA/CD 방법이란

CS : 데이터를 보내려고 하는 컴퓨터가 케이블에 신호가 흐르고 있는지 확인한다

MA : 신호가 흐르지 않는다면 데이터를 보내도 좋다

CD : 충돌이 발생하고 있는지 확인한다.

의 과정을 거칩니다. 하지만 효율이 좋지 않아 CSMA/CD는 거의 사용되지 않습니다.

#### MAC 주소

**랜 카드에는 MAC 주소라는 번호**가 정해져 있습니다. 제조할 때 새겨지기 때문에 **물리 주소**라고도 부르며 **전 세계에서 유일한 번호**로 할당되어 있습니다.

48비트의 숫자로 구성되어 있으며 앞의 24비트는 제조사 번호, 뒤 24비트는 일련번호입니다.

데이터 링크 계층에서 이더넷 헤더와 트레일러를 붙이는데, **이더넷 헤더는 목적지 MAC 주소(6바이트)+출발지 MAC 주소(6바이트)+유형(2바이트)**로 구성되어 있습니다.

이더넷 유형은 이더넷으로 전송되는 상위 계층 프로토콜의 종류를 의미합니다.

**트레일러는 FCS(Frame Check Sequence)라고도 하는데 오류 발생 여부를 확인하는 역할**을 합니다.

**이더넷 헤더와 트레일러가 추가된 데이터를 프레임**이라고 합니다.

#### 스위치

**스위치는 데이터 링크 계층에서 동작**하며 **레이어 2 스위치** 또는 **스위칭 허브**라고 불립니다.

스위치 내부에는 스위치의 포트 번호와 해당 포트에 연결된 컴퓨터의 MAC 주소가 등록 되어 있는 **MAC 주소 테이블**이라는 것이 있습니다.

컴퓨터에 **프레임이 전송되면 MAC 주소 테이블을 확인하고 등록되어 있지 않으면 MAC 주소를 포트와 함께 등록**합니다. 이를 **MAC 주소 학습 기능**이라고 합니다.

스위치는 허브와 다르게 **목적지 MAC 주소가 MAC 주소 테이블에 있다면 해당 포트에만 필터링을 전송(MAC 주소 필터링)**합니다.

**하지만 목적지 MAC 주소가 MAC 주소 테이블에 등록되어 있지 않으면 연결되어 있는 모든 포트에 프레임이 전송**되는데 이 현상을 **플러딩(flooding,홍수**)이라고 부릅니다.

#### 전이중 통신과 반이중 통신

**데이터의 송수신을 동시에 하는 통신 방식을 전이중 통신 방식**이라고 합니다. 데이터를 동시에 전송해도 충돌이 발생하지 않습니다.

**회선 하나로 송신과 수신을 번갈아가면서 하는 통신 방식을 반이중 통신 방식**이라고 합니다. **데이터를 동시에 전송하면 충돌이 발생**합니다.

허브는 송수신이 나누어져 있지 않아 반이중 통신을 사용해야 하지만, 스위치는 충돌이 일어나지 않는 구조로 되어 있어 전이중 통신 방식이 가능합니다.

#### 충돌 도메인

**충돌이 발생할 때 그 범위를 충돌 도메인**이라고 합니다.

허브의 충돌 도메인은 연결되어있는 컴퓨터 전체이며 스위치는 그에 비해 범위가 좁습니다.

#### 이더넷 규격

이더넷은 케이블 종류나 속도에 따라 다양한 규격으로 분류됩니다

10BASE-T를 예시로 들어 10은 통신 속도(Mbps), BASE는 BASEBAND라는 전송 방식, T는 케이블의 종류(UTP)를 의미합니다.

---

모두의 네트워크(저자: 미즈구치 카츠야)를 읽고 정리한 내용입니다.

