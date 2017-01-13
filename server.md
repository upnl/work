유피넬 서버목록
========
[upnl.org] 도메인 소유주는 [heedong] 선배님이니, 네임서버를 바꾸고 싶을경우
이분께 직접 연락해야한다. DNS 서버는 현재 [Cloudflare]를 사용하도록 되어있고,
클라우드플레어 계정은 [simnalamburt]의 개인계정으로 되어있다.

[upnl.org]: http://upnl.org
[heedong]: https://github.com/jinurius
[Cloudflare]: https://cloudflare.com
[simnalamburt]: http://github.com/simnalamburt

<br>

A. 제미니
--------
프로덕션 서버.

유피넬 공식 서비스들이 호스팅되는 서버. 서버관리자와 서비스운영자만이 root
권한을 갖고있고, 일반유저들은 접근할 수 없음.

항목 | 내용
---|---
주소 | [gemini.upnl.org](http://gemini.upnl.org/)
OS | Ubuntu 14.04.5 LTS
위치 | 춘천 IDC
하드웨어 | 일반 탑형 데스크톱

아래와 같은 서비스들이 호스팅되고있음

1.  [유피넬 홈페이지](http://upnl.org/)
1.  [유피넬 깃랩](http://git.upnl.org/)
1.  [UPoTable](http://pokemon.upnl.org/)
1.  [Sentry](http://sentry.upnl.org/)

### `apt`
- git vim-nox zsh fish mosh tmux silversearcher-ag
- nginx htop speedometer fail2ban ntp
- weechat

### `apt` (PPA)
- ruby2.4 ruby2.4-dev ruby-switch - [ppa:brightbox/ruby-ng](https://launchpad.net/~brightbox/+archive/ubuntu/ruby-ng)
- tmux                            - [ppa:pi-rho/dev](https://launchpad.net/~pi-rho/+archive/ubuntu/dev)
- gitlab-ce                       - [packages.gitlab.com](https://about.gitlab.com/downloads/#ubuntu1404)
- mono-complete                   - [download.mono-project.com](http://www.mono-project.com/docs/getting-started/install/linux/)

<br>

B. 소드락
--------
걍 서버.

회칙에 의거하여 모든 유피넬 정회원들은 소드락 계정과 root권한을 받을 수 있음.
정회원들이 돌리고 싶은 서비스들은 아무거나 돌릴 수 있음.

항목 | 내용
---|---
주소 | [sodrak.upnl.org](http://sodrak.upnl.org/)
OS | Ubuntu 14.04.5 LTS
위치 | 302동 서버실
하드웨어 | 랙 유닛 (2U)

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

C. 유리엘
--------
연습장 서버.

회칙에 의거하여 모든 회원들은 유리엘 서버의 계정을 받을 수 있고, 준회원 이상이
될 경우 root권한을 받을 수 있음.

항목 | 내용
---|---
주소 | [uriel.upnl.org](https://uriel.upnl.org/)
OS | Ubuntu 14.04.5 LTS
위치 | 동아리방
하드웨어 | 일반 탑형 데스크톱

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

D. 에델브로이
--------
자고있는 서버.

[선배님께서 기증](https://www.snucse.org/413785)받은 서버로, 타 서버들과 스펙을
비교했을때 성능이 압도적이다. 그런데 아직 유피넬에서 돌리고있는 서비스들중에서
높은 서버사양을 요구하는 서비스가 없어서 그냥 꺼놨음.

항목 | 내용
---|---
주소 | edhelbroy.upnl.org
OS | Xen
위치 | 302동 서버실
하드웨어 | 랙 유닛 (4U half-rack)

원래는 서버관리자 [김지현](https://hyeon.me/)이 이 엄청난 사양을 이용해서 유피넬
회원들마다 가상머신을 하나씩 주자는 원대한 계획을 세우며 받았으나, 공인IP를
여러개 받을 방법이 마땅치 않아 미뤘다는 전설이 있다.
