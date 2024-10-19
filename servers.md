유피넬 서버목록
========
#### Table of contents
1. [edhelbroy](#1-edhelbroy)
2. [sodrak](#2-sodrak)

<br>

## 1. edhelbroy
에델브로이, 학내 프로덕션 서버

[선배님께 기증](https://www.snucse.org/413785)받은 서버이다. 다른 서버들은
평범한 개인용 데스크톱 PC에 리눅스를 설치해서 서버로 쓰는것이어서 어딘가
한두군데 하드웨어 성능이 모자란 부분이 있는 반면, 에델브로이는 애초에 프로덕션
서버로 사용될것을 가정하고 만들어져서 성능이 압도적이다. 자세한 내용은 `/srv/README` 참고.

항목 | 내용
---|---
도메인 | edhelbroy.upnl.org
IP | 147.46.241.87
OS | Debian 10 (codename "buster")
위치 | 서울대학교 302동 서버실 4번 랙
케이스 | 랙 유닛 (4U half-rack)
Mainboard | BIOSTAR TH67B
CPU | Intel Core i7-2600 (quad core, 3.40 GHz)
RAM | DDR3 4GB * 4
Storage | 128GB, Samsung SSD 840 Pro
VGA | *N/A*
PSU | **?**

### 특이사항
- 학교가 암호화되지 않은 트래픽은 감시하기때문에, `cloudflared`를 사용해
  DNS-over-HTTPS를 사용하도록 세팅하였다.
  `/etc/systemd/system/cloudflared-proxy-dns.service` 참고
- <https://ftp.lanet.kr/debian/> 미러를 사용한다. deb.debian.org는 CDN 반응이
  느린 경우가 있어 쓰지 않고, ftp.kr.debian.org는 HTTPS를 지원하지 않아 쓰지
  않는다. HTTPS를 써야만 하는 이유는 학교가 암호화되지 않은 트래픽(특히 HTTP)은
  가로채기 때문이다.
- "main" 리포 외에도 "contrib", "non-free" 리포를 쓴다. 이 머신이 필요로하는
  "rlt_nic/rtl8168e-2.fw" 펌웨어가 non-free여서 어쩔 수 없다.
- gitlab이 22번 포트를 필요로 하기때문에, sshd가 2222번 포트를 사용한다.

### `apt`
- firmware-realtek ca-certificates
- openssh-sever man curl htop git unzip tmux ldnsutils rsync
- fd-find ripgrep fzf fuse
- apt-transport-https gnupg-agent software-properties-common

### `/usr/local/bin`
- k3s
- [nvim](https://github.com/neovim/neovim/releases/tag/v0.4.4), aliased as "vi" and "vim"
- [cloudflared](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/install-and-setup/installation)

&nbsp;

## 2. sodrak
소드락, 걍 서버.

아주 오래된 서버. 최소한 2007년부터는 있었다. 원래 다른 이름으로 돌리던
서버였다가 필요가 없어서 꺼졌는데, 소드락이라는 새 이름을 부여받고 다시 켜졌다.
이**** 선배님의 도움으로, 오랜 과거에는 목동에 있는 KT IDC에서 구동되고 있었고,
그 뒤엔 KT IDC에서 켜져있었다. 그 뒤
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
도메인 | [sodrak.upnl.org](https://sodrak.upnl.org/)
IP | 147.46.242.158
OS | Ubuntu 14.04 LTS
위치 | 302동 서버실, 3번랙
케이스 | 랙 유닛 (2U)
Mainboard | 델 0RH817
CPU | Intel Xeon 3060 (dual core, 2.40 GHz)
RAM | DDR2 2GB × 4
Storage | 465.8GB, 시게이트 ST500DM002-1BD14<br>931.5GB, 웨스턴 디지털 그린 WDC WD10EACS-00D
VGA | ATI ES1000
PSU | **?**

1.  [유피넬 위키](https://wiki.upnl.org)
1.  *아이디*.upnl.org

### `apt`
- mosh zsh fish git htop silversearcher-ag
- htop speedometer fail2ban ntp
- php5 cvs subversion cmake bison ocaml openjdk-7-jdk pandoc redis-server
- virtualbox firefox docker
- python3.4-venv
- debian-goodies ppa-purge
- linux-generic-lts-xenial
- build-essential autoconf libtool bison re2c pkg-config (to compile php 8.1)

### `apt` (PPA)
- ruby2.4 ruby2.4-dev ruby-switch - [ppa:brightbox/ruby-ng](https://launchpad.net/~brightbox/+archive/ubuntu/ruby-ng)
- vim-nox tmux                    - [ppa:pi-rho/dev](https://launchpad.net/~pi-rho/+archive/ubuntu/dev)
- nodejs                          - [deb.nodesource.com/setup_6.x](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)
- g++-8                           - [ppa:jonathonf/gcc](https://launchpad.net/~jonathonf/+archive/ubuntu/gcc)

### `/usr/local/bin`
- [Caddy](https://caddyserver.com) (`/usr/local/bin/caddy`, `/etc/init/caddy.conf`, `/etc/caddy/Caddyfile`)
- [ripgrep](https://github.com/BurntSushi/ripgrep/releases)
