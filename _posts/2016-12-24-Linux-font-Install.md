---
layout: post
title: RaspberryPi / Linux 폰트 설치
tags:
- RaspberryPi
- Linux
- font
- 설치
---

## 개요
RaspberryPi를 TV에 연결해서 애니를 보고 있다. 일반적으로 smi 자막으로 볼 때는 딱히 문제가 없었는데, ass 자막을 이용하려면 자막 제작자가 제공하는 폰트를 설치 해야 했다. 윈도우 환경에서는 폰트 파일을 실행하기만 하면 바로 설치가 가능했다. 하지만 리눅스 환경에서 SSH를 통한 원격 접속으로 폰트를 설치 하는데는 그 방법은 쓸 수 없다.

## 폰트 설치
폰트를 설치하기 위해서는 font-manager[^font-manager] 패키지가 필요하다. 아래 명령을 통해 font-manager를 설치하자.

```bash
sudo apt-get install font-manager
```
먼저 설치된 폰트목록을 `fc-list` 명령으로 조회해 본다.

![추가 전 목록](https://dl.dropboxusercontent.com/u/14359304/Blog%20Images/Linux-font-Install_%EC%B6%94%EA%B0%80%20%EC%A0%84%20%EB%AA%A9%EB%A1%9D.png)

그리고, 테스트용 영상을 틀어 본다.

![추가 전 영상]()

system에서 관리하는 폰트 디렉토리[^font_dictory][^font_dictory2]로 설치할 폰트를 옮긴다.
시스템 디렉토리 이므로 루트 권한을 주거나 `sudo` 명령어를 사용한다.

```bash
sudo mv 'fontfile' /usr/share/fonts/
```

폰트를 옮긴 후, font-manager에 `fc-cache`[^fc-cache] 명령으로 폰트 파일들을 font cahche에 추가한다.

```bash
fc-cache -fv
```

## 확인
적용이 끝나면, 폰트가 추가 되었는지 확인 한다.

```bash
fc-list
```

![추가 후 목록](https://dl.dropboxusercontent.com/u/14359304/Blog%20Images/Linux-font-Install_%EC%B6%94%EA%B0%80%20%ED%9B%84%20%EB%AA%A9%EB%A1%9D.png)

이제 ass 자막에 폰트가 적용 됐는지 확인한다.

![추가 후 영상]()


---
[^font-manager]: https://wiki.debian.org/Fonts/#Adding_fonts
[^fc-cache]: -f 옵션은 강제 스캔, -v 옵션은 과정 출력.
[^font_dictory]: `/usr/share/fonts/` 하위 디렉토리도 인식된다.
[^font_dictory2]: 하위 디렉토리도 인식된다.
