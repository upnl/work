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

최소한 2008년부터 유피넬 동방에 있었던 컴퓨터. 원래는 학교 컴퓨터였다. (제미니
옛 본체에 서울대학교 자산이라는 표시가 있음) 학교에서 기증받은건지, 아니면
버리는 컴퓨터를 동아리에서 줏어온건지, 알 수 없는 과정을 통해 유피넬의 컴퓨터가
되었다. 하드디스크도 여러번 고장나고 업그레이드를 계속하다가 애물단지가 되어
이를 버리게되자, [2015년 3월 27일에 김지현이 이를 포맷하여 서버로
만든다.](http://upnl.org/336)

유피넬 공식 서비스들이 호스팅되는 서버. 서버관리자와 서비스운영자만이 root
권한을 갖고있고, 일반유저들은 접근할 수 없음.

항목 | 내용
---|---
주소 | [gemini.upnl.org](http://gemini.upnl.org/)
IP | 121.166.66.24
OS | Ubuntu 14.04.5 LTS
위치 | 김지현의 집
케이스 | COX A3 노빌레 풀아크릴윈도우 with 헤일로X4 블랙
Mainboard | 기가비트 GA-MA770-US3
CPU | AMD Phenom 8750 (triple core, 2.40 GHz)
RAM | DDR2 1GB×2 + 2GB×2
Storage | 465.8GB, 시게이트 ST500DM002-1BD14
VGA | *N/A*
PSU | 슈퍼플라워 SF-500R14SE Silver Green FX

아래와 같은 서비스들이 호스팅되고있음

1. [유피넬 깃랩](https://git.upnl.org)
1. [유피넬 홈페이지](https://upnl.org)
1. [UPoTable](https://pokemon.upnl.org)
1. [Helix](https://helix.upnl.org)

### `apt`
- git vim-nox fish
- htop fail2ban ntp
- linux-generic-lts-xenial

### `apt` (PPA)
- redis-server                    - [ppa:chris-lea/redis-server](https://launchpad.net/~chris-lea/+archive/ubuntu/redis-server)
- docker-ce                       - [download.docker.com](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/)
- gitlab-ce                       - [packages.gitlab.com](https://about.gitlab.com/installation/#ubuntu)
- mosh                            - [ppa:keithw/mosh](https://launchpad.net/~keithw/+archive/ubuntu/mosh)
- tmux                            - [ppa:pi-rho/dev](https://launchpad.net/~pi-rho/+archive/ubuntu/dev)

### etc
- [Caddy](https://caddyserver.com) (`/usr/local/bin/caddy`, `/etc/init/caddy.conf`, `/etc/caddy/Caddyfile`)
- [ripgrep](https://github.com/BurntSushi/ripgrep/releases)

### Note
- ssh 포트 2222로 변경됨
- 도커 설치한 뒤, 스토리지 드라이버를 [`overlay2`](https://docs.docker.com/engine/userguide/storagedriver/overlayfs-driver/)로 바꿔줬음

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
케이스 | 랙 유닛 (4U half-rack)
Mainboard | BIOSTAR TH67B
CPU | Intel Core i7-2600 (quad core, 3.40 GHz)
RAM | DDR3 4GB * 4
Storage | 60GB, 삼성 SSD 830<br>2TB, 히타치 HDD723020BLA642
VGA | *N/A*
PSU | **?**

### `apt`
- linux-generic-hwe-16.04
- htop mosh

**삭제한 패키지 목록**

- byobu snapd

한때 서버관리자 [김지현](https://hyeon.me/)이 에델브로이의 엄청난 사양을
이용해서 유피넬 회원들마다 가상머신을 하나씩 주자는 장밋빛 미래를 꿈꿨으나,
충분한 수의 공인IP를 확보할 방법이 마땅치 않아 그만뒀다.

<br>

## 3. sodrak
소드락, 걍 서버.

아주 오래된 서버. 최소한 2007년부터는 있었다. 원래 다른 이름으로 돌리던
서버였다가 필요가 없어서 꺼졌는데, 소드락이라는 새 이름을 부여받고 다시 켜졌다.
이**** 선배님을 통해 분당에 있는 KT IDC에서 오랜시간 돌아가다가, 월 8만원
이용료의 부담이 점점 강해져서 2016년 1월 27일 IDC에서 나오게되었다. (관련기록:
IRC 로그) 이후엔 김지현의 춘천 본가에서 돌리다가, 2016년 여름 전기료 누진율
폭탄때문에 2016년 9월 학교로 옮기게되었다. (관련기록: [1] [2] [3])

[1]: https://twitter.com/simnalamburt/status/777050904016986113
[2]: https://twitter.com/simnalamburt/status/777507395631132673
[3]: https://twitter.com/simnalamburt/status/777509134035918849

회칙에 의거하여 모든 유피넬 정회원들은 소드락 계정과 root권한을 받을 수 있음.
정회원들이 돌리고 싶은 서비스들은 아무거나 돌릴 수 있음.

항목 | 내용
---|---
주소 | [sodrak.upnl.org](http://sodrak.upnl.org/)
IP | 147.46.242.158
OS | Ubuntu 14.04 LTS
위치 | 302동 서버실
케이스 | 랙 유닛 (2U)
Mainboard | 델 0RH817
CPU | Intel Xeon 3060 (dual core, 2.40 GHz)
RAM | DDR2 2GB × 4
Storage | 465.8GB, 시게이트 ST500DM002-1BD14<br>931.5GB, 웨스턴 디지털 그린 WDC WD10EACS-00D
VGA | ATI ES1000
PSU | **?**

1.  [유피넬 위키](http://wiki.sodrak.upnl.org/)
1.  [노나메용 위키](http://old.wiki.sodrak.upnl.org/)
1.  *아이디*.upnl.org

### `apt`
- mosh zsh fish git htop silversearcher-ag
- htop speedometer fail2ban ntp
- php5 cvs subversion cmake bison ocaml openjdk-7-jdk pandoc redis-server
- virtualbox firefox docker
- python3.4-venv
- debian-goodies ppa-purge
- linux-generic-lts-xenial

### `apt` (PPA)
- apache2                         - [ppa:ondrej/apache2](https://launchpad.net/~ondrej/+archive/ubuntu/apache2)
- ruby2.4 ruby2.4-dev ruby-switch - [ppa:brightbox/ruby-ng](https://launchpad.net/~brightbox/+archive/ubuntu/ruby-ng)
- vim-nox tmux                    - [ppa:pi-rho/dev](https://launchpad.net/~pi-rho/+archive/ubuntu/dev)
- nodejs                          - [deb.nodesource.com/setup_6.x](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)
- irssi                           - [irssi.org](https://irssi.org/download/)
- weechat-curses weechat-plugins  - [weechat.org](https://weechat.org/download/debian/#instructions)

### etc
- [Caddy](https://caddyserver.com) (`/usr/local/bin/caddy`, `/etc/init/caddy.conf`, `/etc/caddy/Caddyfile`)
- [ripgrep](https://github.com/BurntSushi/ripgrep/releases)

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
케이스 | 빅타워 케이스
Mainboard | 기가비트 P55-UD3
CPU | Intel Core i5-750 (quad core, 2.67 GHz)
RAM | DDR3 2GB × 1
Storage | 298.1GB, 웨스턴 디지털 블루 WDC WD3200AAJS-0
VGA | MGA 2064W
PSU | **?**

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

