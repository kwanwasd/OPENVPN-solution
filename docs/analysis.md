# 주요 원인 판별 (Why)

## 1) 네트워크/방화벽 차단
- `ping <SERVER_IP>` 실패, `nc -vuz <SERVER_IP> 1194` 실패 시 의심
- **iptables 최상단 DROP**, UFW deny, 클라우드 보안그룹 미허용 여부 확인  
**[방화벽 차단 증거]** → `images/fw_drop_top.png`

## 2) TLS/인증 불일치
- 시간 오차, 인증서 만료/CN 불일치, 암호/해시/키 옵션 불일치
- `tls-crypt`/`tls-auth`, `verify-x509-name`, `remote-cert-tls` 점검

## 3) 계정/권한
- 계정 잠금/만료, 동시 접속 제한, IP 풀 고갈
- RADIUS/LDAP 연동 시 서버 인증 로그 동시 확인

## 4) 라우팅/DNS/스플릿 터널
- 서버 `push`(redirect-gateway/route/dhcp-option DNS), 서버 NAT/IP 포워딩

## 5) MTU/MSS/품질
- 큰 패킷만 실패 시 MTU/MSS 의심 → `ping -M do -s 1472 8.8.8.8` 등으로 테스트
