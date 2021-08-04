퇴역한 서버들
========
#### Table of contents
1. [uriel](#1-uriel)
2. [gemini](#2-gemini)
3. [ebony](#3-ebony)

<br>

## 1. uriel
유리엘, 연습장 서버.

회칙에 의거하여 모든 회원들은 유리엘 서버의 계정을 받을 수 있고, 준회원 이상이
될 경우 root권한을 받을 수 있음.

고장나서 버렸다.

항목 | 내용
---|---
도메인 | [uriel.upnl.org](https://uriel.upnl.org/), <username>.uriel.upnl.org
OS | Ubuntu 14.04.5 LTS
위치 | 동아리방
케이스 | 빅타워 케이스
Mainboard | 기가비트 P55-UD3
CPU | Intel Core i5-750 (quad core, 2.67 GHz)
RAM | DDR3 2GB × 1
Storage | 298.1GB, 웨스턴 디지털 블루 WDC WD3200AAJS-0
VGA | MGA 2064W
PSU | **?**

### `apt`
- tmux *(1.8.5 버전으로 고정)*
- mosh zsh fish git htop silversearcher-ag
- htop fail2ban ntp
- nginx mysql-server
- mono-runtime mono-devel
- g++-6 firefox docker.io cmake
- python3.4-venv
- debian-goodies ppa-purge
- linux-generic-lts-xenial

### `apt` (PPA)
- ruby2.4 ruby2.4-dev ruby-switch - [ppa:brightbox/ruby-ng](https://launchpad.net/~brightbox/+archive/ubuntu/ruby-ng)
- vim-nox                         - [ppa:pi-rho/dev](https://launchpad.net/~pi-rho/+archive/ubuntu/dev)
- nodejs                          - [deb.nodesource.com/setup_6.x](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)
- irssi                           - [irssi.org](https://irssi.org/download/)
- weechat-curses weechat-plugins  - [weechat.org](https://weechat.org/download/debian/#instructions)

### etc
- [Caddy](https://caddyserver.com) (`/usr/local/bin/caddy`, `/etc/init/caddy.conf`, `/etc/caddy/Caddyfile`)

<br>

## 2. gemini
제미니, 학외 프로덕션 서버.

최소한 2008년부터 유피넬 동방에 있었던 컴퓨터. 원래는 학교 컴퓨터였다. (제미니
옛 본체에 서울대학교 자산이라는 표시가 있음) 학교에서 기증받은건지, 아니면
버리는 컴퓨터를 동아리에서 줏어온건지, 알 수 없는 과정을 통해 유피넬의 컴퓨터가
되었다. 하드디스크도 여러번 고장나고 업그레이드를 계속하다가 애물단지가 되어
이를 버리게되자, [2015년 3월 27일에 김지현이 이를 포맷하여 서버로
만든다.](https://upnl.org/336)

유피넬 공식 서비스들이 호스팅되는 서버. 서버관리자와 서비스운영자만이 root
권한을 갖고있고, 일반유저들은 접근할 수 없음.

서버로 오랫동안 쓰다가, 2019년 말부터 AWS로 조금씩 이전하였고, 2020년 4월 4일
마지막으로 남아있던 GitLab도 AWS로 이전되면서 용도를 다하였다.

항목 | 내용
---|---
도메인 | gemini.upnl.org
OS | Ubuntu 18.04 LTS
위치 | 김지현의 집
케이스 | COX A3 노빌레 풀아크릴윈도우 with 헤일로X4 블랙
Mainboard | 기가비트 GA-MA770-US3
CPU | AMD Phenom 8750 (triple core, 2.40 GHz)
RAM | DDR2 1GB×2 + 2GB×2
Storage | 465.8GB, 시게이트 ST500DM002-1BD14
VGA | *N/A*
PSU | 슈퍼플라워 SF-500R14SE Silver Green FX

### `apt`
- curl git htop

### `apt` (PPA)
- [docker-ce](https://docs.docker.com/install/linux/docker-ce/ubuntu/) `5:19.03.6~3-0~ubuntu-bionic`
- docker-ce-cli `5:19.03.6~3-0~ubuntu-bionic`
- containerd.io

### etc
- [Caddy](https://caddyserver.com) (`/usr/local/bin/caddy`, `/etc/caddy/Caddyfile`)

### Note
- ssh 포트 2222로 변경됨

<br>

## 3. ebony
에보니, AWS 프로덕션 서버. 유피넬 공식 서비스들이 호스팅되는 서버. 서버관리자와
서비스운영자만이 root 권한을 갖고있고, 일반유저들은 접근할 수 없음.

서버에 관한 상세 정보는 [upnl/infra](https://github.com/upnl/infra)의 테라폼
코드를 참고바람.

비용문제로 폐기됨.
