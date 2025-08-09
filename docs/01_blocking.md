01_blocking.md
markdown
복사
편집
# 1. VPN 차단 과정 (Blocking)

## 목적
의도적으로 VPN 접속 실패를 만들어 이후 **확인 → 해결 → 결과**를 테스트한다.

## 대상
- OS: **Linux**
- VPN: **OpenVPN** (기본 1194/UDP 포트)

## 사용한 차단 방식
UFW(Uncomplicated Firewall)로 VPN 포트(UDP 1194) 차단

---

### 1) 차단 명령
```bash
sudo ufw deny 1194/udp
2) 상태 확인
bash
복사
편집
sudo ufw status numbered
기대 실패 로그 예시

vbnet
복사
편집
TLS Error: TLS key negotiation failed to occur within 60 seconds
Inactivity timeout (--ping-restart)
증빙 스크린샷
![VPN 차단 스크린샷](https://github.com/kwanwasd/OPENVPN-solution/raw/a435a05ded3a2cfb2793408637df510c0f9fee0f/docs/images/vpn%20%EB%A7%89%EC%9D%8C%202.jpg)


3) 빠른 원복 명령
bash
복사
편집
sudo ufw delete deny 1194/udp || true
yaml
복사
편집

---
