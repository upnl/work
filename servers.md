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
OS | Debian 12 (codename "bookworm")
위치 | 서울대학교 302동 서버실 4번 랙
케이스 | 랙 유닛 (4U half-rack)
Mainboard | BIOSTAR TH67B
CPU | Intel Core i7-2600 (quad core, 3.40 GHz)
RAM | DDR3 4GB * 4
Storage | 256GB * 2 MIRROR, Samsung SSD PM9B1
VGA | *N/A*
PSU | **?**

### 특이사항

- UEFI boot 파티션으로 nvme ssd를 사용할 수 없어 부트 디스크는 이전에 사용하던 SATA3 기반 ssd를 사용중이다. 


### `/usr/local/bin`
- **k0s**
- [nvim](https://github.com/neovim/neovim/releases/tag/v0.4.4), aliased as "vi" and "vim"

---

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
OS | Arch Linux 
위치 | 302동 서버실, 3번랙
케이스 | 랙 유닛 (2U)
Mainboard | 델 0RH817
CPU | Intel Xeon 3060 (dual core, 2.40 GHz)
RAM | DDR2 2GB × 4
Storage | 465.8GB, Seagate ST500DM002-1BD14 (/boot, swap, BIOS boot partition) & 931.5GB, WD Green WDC WD10EACS-00D (/home) & 256GB Samsung SSD PM9B1 (/)
VGA | ATI ES1000
PSU | **?**

### 특이사항

- btrfs mirror를 적용할 에정이었으나, 메인보드가 PCI-e 이중화를 지원하지 않아 장착한 PM9B1 ssd 2개 중 하나만 읽히고 있는 상황.
  - CD 리더를 제거하고 확장카드를 넣어서 쓰거나, 아니면 다른 자원으로 옮기기 필요
- 메인보드의 BIOS가 상당히 옛날 것이라, UEFI 부트로더를 이용할 수 없어 MBR BIOS Boot Partition을 이용하였다.
  - 재설치시 이를 유념하여 grub 설치에 BIOS boot partition 설치 매뉴얼을 확인할 것.
