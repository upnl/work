유피넬 서버목록
========
[upnl.org] 도메인 소유주는 [heedong] 선배님이니, 네임서버를 바꾸고 싶을경우
이분께 직접 연락해야한다. DNS 서버는 현재 [Cloudflare]를 사용하도록 되어있고,
클라우드플레어 계정은 [simnalamburt]의 개인계정으로 되어있다.

[upnl.org]: http://upnl.org
[heedong]: https://github.com/jinurius
[Cloudflare]: https://cloudflare.com
[simnalamburt]: http://github.com/simnalamburt

#### Table of contents
1. [gemini](#1-gemini)
2. [edhelbroy](#2-edhelbroy)
3. [sodrak](#3-sodrak)
4. [uriel](#4-uriel)

<br>

## 1. gemini
제미니, 학외 프로덕션 서버.

유피넬 공식 서비스들이 호스팅되는 서버. 서버관리자와 서비스운영자만이 root
권한을 갖고있고, 일반유저들은 접근할 수 없음.

항목 | 내용
---|---
주소 | [gemini.upnl.org](http://gemini.upnl.org/)
IP | 211.218.61.123
OS | Ubuntu 14.04.5 LTS
위치 | 춘천 IDC
하드웨어 | 일반 탑형 데스크톱
Mainboard | 기가비트 GA-MA770-US3
CPU | AMD Phenom 8750 (triple core, 2.40 GHz)
RAM | DDR2 1GB×2 + 2GB×2
Storage | 465.8GB, 시게이트 ST500DM002-1BD14
VGA | GeForce 9500 GT

아래와 같은 서비스들이 호스팅되고있음

1.  [유피넬 홈페이지](http://upnl.org/)
1.  [유피넬 깃랩](http://git.upnl.org/)
1.  [UPoTable](http://pokemon.upnl.org/)
1.  [Sentry](http://sentry.upnl.org/)

### `apt`
- git vim-nox zsh fish mosh tmux silversearcher-ag
- nginx htop speedometer fail2ban ntp
- weechat
- linux-signed-generic-lts-xenial

### `apt` (PPA)
- ruby2.4 ruby2.4-dev ruby-switch - [ppa:brightbox/ruby-ng](https://launchpad.net/~brightbox/+archive/ubuntu/ruby-ng)
- tmux                            - [ppa:pi-rho/dev](https://launchpad.net/~pi-rho/+archive/ubuntu/dev)
- gitlab-ce                       - [packages.gitlab.com](https://about.gitlab.com/downloads/#ubuntu1404)
- mono-complete                   - [download.mono-project.com](http://www.mono-project.com/docs/getting-started/install/linux/)
- docker-engine                   - [download.docker.com](https://docs.docker.com/engine/installation/linux/ubuntu/)

### Note
- 도커 설치한 뒤, 스토리지 드라이버를 [`overlay2`](https://docs.docker.com/engine/userguide/storagedriver/overlayfs-driver/)로 바꾸는것을 잊지 말것.

<br>

## 2. edhelbroy
에델브로이, 학내 프로덕션 서버

[선배님께 기증](https://www.snucse.org/413785)받은 서버이다. 다른 서버들은
평범한 개인용 데스크톱 PC에 리눅스를 설치해서 서버로 쓰는것이어서 어딘가
한두군데 하드웨어 성능이 모자란 부분이 있는 반면, 에델브로이는 애초에 프로덕션
서버로 사용될것을 가정하고 만들어져서 성능이 압도적이다.

아직 대부분의 서비스들이 제미니에 올라가있다. 제미니에 있는 서비스들을 하나하나
도커로 감싸 에델브로이로 이전해야한다.

항목 | 내용
---|---
주소 | [edhelbroy.upnl.org](http://edhelbroy.upnl.org/)
IP | 147.46.242.115
OS | Ubuntu 16.04 LTS
위치 | 서울대학교 302동 서버실
하드웨어 | 랙 유닛 (4U half-rack)
Mainboard | BIOSTAR TH67B
CPU | Intel Core i7-2600 (quad core, 3.40 GHz)
RAM | DDR3 4GB * 4
Storage | 60GB, 삼성 SSD 830<br>2TB, 히타치 HDD723020BLA642
VGA | *N/A*

### `apt`
- linux-generic-hwe-16.04
- nginx htop mosh
- python3-venv

한때 서버관리자 [김지현](https://hyeon.me/)이 에델브로이의 엄청난 사양을
이용해서 유피넬 회원들마다 가상머신을 하나씩 주자는 장밋빛 미래를 꿈꿨으나,
충분한 수의 공인IP를 확보할 방법이 마땅치 않아 그만뒀다.

<br>

## 3. sodrak
소드락, 걍 서버.

회칙에 의거하여 모든 유피넬 정회원들은 소드락 계정과 root권한을 받을 수 있음.
정회원들이 돌리고 싶은 서비스들은 아무거나 돌릴 수 있음.

항목 | 내용
---|---
주소 | [sodrak.upnl.org](http://sodrak.upnl.org/)
IP | 147.46.242.158
OS | Ubuntu 14.04 LTS
위치 | 302동 서버실
하드웨어 | 랙 유닛 (2U)
Mainboard | 델 0RH817
CPU | Intel Xeon 3060 (dual core, 2.40 GHz)
RAM | DDR2 2GB × 4
Storage | 465.8GB, 시게이트 ST500DM002-1BD14<br>931.5GB, 웨스턴 디지털 그린 WDC WD10EACS-00D
VGA | ATI ES1000

1.  [유피넬 위키](http://wiki.sodrak.upnl.org/)
1.  [노나메용 위키](http://old.wiki.sodrak.upnl.org/)
1.  *아이디*.upnl.org

### `apt`
- mosh zsh fish git htop silversearcher-ag
- htop speedometer fail2ban ntp
- apache2 php5 cvs subversion cmake bison ocaml openjdk-7-jdk pandoc redis-server
- virtualbox firefox docker
- python3.4-venv
- debian-goodies ppa-purge
- linux-generic-lts-xenial linux-image-extra-virtual

### `apt` (PPA)
- ruby2.4 ruby2.4-dev ruby-switch - [ppa:brightbox/ruby-ng](https://launchpad.net/~brightbox/+archive/ubuntu/ruby-ng)
- vim-nox tmux                    - [ppa:pi-rho/dev](https://launchpad.net/~pi-rho/+archive/ubuntu/dev)
- nodejs                          - [deb.nodesource.com/setup_6.x](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)
- irssi                           - [irssi.org](https://irssi.org/download/)
- weechat-curses weechat-plugins  - [weechat.org](https://weechat.org/download/debian/#instructions)

<br>

## 4. uriel
유리엘, 연습장 서버.

회칙에 의거하여 모든 회원들은 유리엘 서버의 계정을 받을 수 있고, 준회원 이상이
될 경우 root권한을 받을 수 있음.

항목 | 내용
---|---
주소 | [uriel.upnl.org](https://uriel.upnl.org/)
IP | 147.46.113.114
OS | Ubuntu 14.04.5 LTS
위치 | 동아리방
하드웨어 | 일반 탑형 데스크톱
Mainboard | 기가비트 P55-UD3
CPU | Intel Core i5-750 (quad core, 2.67 GHz)
RAM | DDR3 2GB × 1
Storage | 298.1GB, 웨스턴 디지털 블루 WDC WD3200AAJS-0
VGA | MGA 2064W

1.  *아이디*.uriel.upnl.org (HTTPS Only)

### `apt`
- tmux *(1.8.5 버전으로 고정)*
- mosh zsh fish git htop silversearcher-ag
- htop fail2ban ntp
- nginx mysql-server
- mono-runtime mono-devel
- g++-6 firefox docker.io cmake
- python3.4-venv
- debian-goodies ppa-purge
- linux-generic-lts-xenial linux-image-extra-virtual

### `apt` (PPA)
- ruby2.4 ruby2.4-dev ruby-switch - [ppa:brightbox/ruby-ng](https://launchpad.net/~brightbox/+archive/ubuntu/ruby-ng)
- vim-nox                         - [ppa:pi-rho/dev](https://launchpad.net/~pi-rho/+archive/ubuntu/dev)
- nodejs                          - [deb.nodesource.com/setup_6.x](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)
- irssi                           - [irssi.org](https://irssi.org/download/)
- weechat-curses weechat-plugins  - [weechat.org](https://weechat.org/download/debian/#instructions)

<br>

