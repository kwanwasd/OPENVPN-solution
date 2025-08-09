01. 막는 과정 (Linux - UFW 단일 방식)
목적: 의도적으로 VPN 접속 실패를 만들어 이후 확인 → 해결 → 결과를 테스트한다.
대상: Linux, OpenVPN(기본 1194/UDP)

내가 막은 방식
UFW로 VPN 포트 차단 (UDP 1194 기준)

실행 명령
bash
복사
편집
# 차단
sudo ufw deny 1194/udp

# 상태 확인
sudo ufw status numbered
기대 실패 로그
TLS Error: TLS key negotiation failed to occur within 60 seconds

Inactivity timeout (--ping-restart)

증빙 스크린샷

빠른 원복
bash
복사
편집
sudo ufw delete deny 1194/udp || true
