# 해결 절차 (How to fix)

## 1) 방화벽 차단 해제 (서버)
- UFW 허용: `sudo ufw allow 1194/udp`
- UFW 차단 삭제: `sudo ufw delete deny 1194/udp`
- iptables 최상단 차단 삭제: `sudo iptables -D INPUT 1`
- iptables 허용 규칙 추가(예):  
  `sudo iptables -I INPUT 1 -p udp --dport 1194 -j ACCEPT`

**[방화벽 수정 화면]** → `images/fw_allow.png` (캡션: 차단 삭제 & 허용 추가)

## 2) TLS/인증 오류 조치
- 시간 동기화 후 재시도, 인증서 만료/CN 불일치 해결
- 암호 스위트/해시/키/방향 옵션 일치

## 3) 라우팅/DNS 조정(필요 시)
- `push` 옵션, NAT, IP 포워딩 확인
