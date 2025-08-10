### **03_testing.md**
markdown
# 3. 차단/허용 테스트 과정 (Testing)

## 테스트 환경
- 클라이언트: Linux
- VPN 서버: Ubuntu Server (OpenVPN)

---

### 1) 차단 상태에서 접속 시도
bash
sudo openvpn --config client.ovpn
예상 결과: 접속 실패 (TLS Error)

2) 허용 상태에서 접속 시도
bash
복사
편집
sudo openvpn --config client.ovpn
예상 결과: 접속 성공 (Initialization Sequence Completed 출력)

차단 상태:

[image](./images/vpn안됨.png)

허용 상태:

[image](./images/연결성공.png)

yaml
복사
편집

---
