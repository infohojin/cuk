---
layout: home
---

# 02. 서비스 거부 공격







## 학습목표

* 서비스 거부 공격의 정의와 유형을 살펴 봅니다.
* TCP SYN Flood의 작동원리와 대책을 이해합니다.
* Smurf 공격의 작동원리와 대책을 이해합니다.
* Ping of Death의 작동원리와 대책을 이해합니다.
* 분산 Dos 공격의 작동원리와 대책을 이해 합니다.



## 학습목차

[서비스 거부 공격의 개요](01)

TCP SYN Flood

Smurf 공격

Ping of Death

분산 Dos 공격





TCP Sync Flood![](./img/security02_10.png)

![](./img/security02_11.png)

![](./img/security02_12.png)

![](./img/security02_13.png)

![](./img/security02_14.png)

![](./img/security02_15.png)

![](./img/security02_16.png)

![](./img/security02_17.png)

![](./img/security02_18.png)

![](./img/security02_19.png)

![](./img/security02_20.png)

![](./img/security02_21.png)

![](./img/security02_22.png)

![](./img/security02_23.png)

![](./img/security02_24.png)

![](./img/security02_25.png)

![](./img/security02_26.png)

![](./img/security02_27.png)

![](./img/security02_28.png)

![](./img/security02_29.png)

![](./img/security02_30.png)

![](./img/security02_31.png)

![](./img/security02_32.png)

![](./img/security02_33.png)

![](./img/security02_34.png)

![](./img/security02_35.png)

![](./img/security02_36.png)

![](./img/security02_37.png)

![](./img/security02_38.png)



## 학습정리

1. `서비스 거부 공격`은 시스템 자원에 대한 가용성을 잦추거나 시스템을 정상적으로 이용할 수 없는 상태로 만들려는 목적을 가집니다.
2. `TCP SYN flood`는 TCP의 3단계 핸드쉐이크 과정에 따른 취약점을 이용하며, 방화벽의 사용이나 접속 큐의 조정으로 방지할 수 있습니다.
3. `Smurf 공격`은 브로드캐스트 주소를 사용하는 ICMP의 취약점을 이용하며, 라우터나 호스트에서 ping 요청을 거부하도록 하여 방지할 수 있습니다.
4. `ping of Death` 는 IP다편화에 따른 재조립 과정에서 오류를 발생하는 운영체제의 버그를 이용하ㅕ, 패치를 설치하여 방지할 수 있습니다.
5. `분산 Dos 공격`은 공격 대상의 중간 지점에 있는 다수의 에이전트를 공격에 참여하도록 하며, 안티바이러스, 방화벽 필터링 기능, 트래픽 우회등으로 방지할 수 있습니다.