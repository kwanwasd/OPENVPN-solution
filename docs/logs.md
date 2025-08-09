# 재현 & 로그 수집

## 클라이언트 로그
가능하시다면 **GUI 로그 또는 CLI 로그**를 수집해 주십시오. 핵심 키워드는 **TLS 오류**, **인증 실패**, **포트 접근 실패**입니다.

- **Windows**: `C:\\Program Files\\OpenVPN\\log\\*.log` 확인 또는 GUI에서 **View Log** 저장  
- **Windows(CLI)**: `openvpn.exe --config client.ovpn --remote <SERVER> <PORT> <PROTO>`  
- **Linux**: `sudo openvpn --config client.ovpn --remote <SERVER> <PORT> <PROTO>`  
- **macOS(Homebrew)**: `sudo openvpn --config client.ovpn --remote <SERVER> <PORT> <PROTO>`

**[클라이언트 로그 예시]** → `images/client_log.png` (캡션: TLS 핸드셰이크 실패 예시)

## 서버 확인
- 서비스 상태: `sudo systemctl status openvpn-server`  
- 포트/프로세스: `sudo ss -lunpt | grep -E 'openvpn|:1194'`  
- 방화벽: `sudo ufw status numbered` / `sudo iptables -L -n --line-numbers`

**[서버 포트/방화벽 확인]** → `images/server_firewall.png` (캡션: 1194/udp 리스닝 & 허용 여부)
