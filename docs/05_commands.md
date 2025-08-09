# 5. 사용 명령어 (Commands Used)
• 클라이언트 접속: sudo openvpn --config [파일명].ovpn
• UFW 방화벽 규칙을 번호와 함께 확인: sudo ufw status numbered
• UFW 허용: sudo ufw allow 1194/udp
• UFW 차단 삭제: sudo ufw delete deny 1194/udp
• iptables 목록: sudo iptables -L -n --line-numbers
• iptables 규칙 추가: sudo iptables -I INPUT 1 -p udp --dport 1194 -j DROP
• iptables 삭제(1 번 규칙): sudo iptables -D INPUT 1
