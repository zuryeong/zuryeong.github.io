---
layout: post
title: RaspberryPi B+ Plex Media Server 설치기.
tags:
- RaspberryPi
- Linux
- PlexMediaServer
- 설치
---
# RaspberryPi B+ Plex Media Server 설치기

## 개요

RaspberryPi에서 Plex Media Server를 사용하기 위해서 처음에는 RasPlex라는 것을 설치해서 사용 해보았지만, 이건 단순히 Plex 서버에서 미디어를 읽기 위한 Client 일 뿐이었다. 그리고, OpenELEC 기반이면서 apt-get을 사용할 수도 없었다.
 그래서 RaspberryPi에 Plex Media Server와 Plex Client 둘 다 깔아서, TV에 직접 연결하는 미디어 센터 겸 NAS를 구축하기로 했다.

## OS 설치

 처음에는 라즈비안을 기반으로 하려고 했지만, 가지고 있는 RaspberryPi가 구형이라 버벅였다. 그래서 CUI 환경에 가볍고, 페도라나 데비안 계열에 RaspberryPi에 설치가 가능한 [Minibian](https://minibianpi.wordpress.com)을 선택했다.

* 이미지 다운로드
* Win32DiskImager를 이용해 MicroSD에 설치
* RaspberryPi 부팅 후 초기 설정
  * 초기 계정
    * id : root
    * password : raspberry
  * 개인 계정 생성
  * sudo 그룹에 추가
* sudo 패키지 설치[^sudo]

* 참조 : <https://pimylifeup.com/raspberry-pi-plex-server/>



 [^sudo]: Minibian에 `sudo` 패키지가 설치되어 있지 않아서, `sudo` 명령이 안먹힌다.
