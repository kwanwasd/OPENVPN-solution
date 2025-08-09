# 부록 (치트시트/템플릿)

## 명령어 치트시트
- 클라이언트: `sudo openvpn --config client.ovpn --remote <SERVER> <PORT> <PROTO>`
- UFW: `sudo ufw status numbered` / `sudo ufw allow 1194/udp` / `sudo ufw delete deny 1194/udp`
- iptables: `sudo iptables -L -n --line-numbers` / `sudo iptables -I INPUT 1 -p udp --dport 1194 -j ACCEPT` / `sudo iptables -D INPUT 1`
- 서버 로그: `sudo journalctl -u openvpn-server -b --no-pager`
- 리스닝 확인: `sudo ss -lunpt | grep -E 'openvpn|:1194'`

## 커뮤니케이션 템플릿
- 정보 요청: “사용자 환경(망/OS/클라이언트 버전)과 오류 시각/메시지를 보내 주세요.”
- 진행 안내: “먼저 네트워크/방화벽 상태를 점검하고 필요 시 원격 세션을 요청드리겠습니다.”
- 종료 보고: “최상단 DROP 규칙이 원인이었고, 제거 후 1194/udp 허용으로 정상 확인했습니다.”
