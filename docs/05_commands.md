05_troubleshooting.md
markdown
복사
편집
# 5. 문제 해결 (Troubleshooting)

## 1) 포트 차단이 안 되는 경우
- UFW가 활성화되어 있는지 확인
bash
sudo ufw status
sudo ufw enable
2) 방화벽 외 다른 보안 소프트웨어 확인
iptables 규칙, 클라우드 보안 그룹(Security Group) 등 확인 필요

3) 포트가 이미 다른 서비스에서 사용 중인 경우
bash
복사
편집
sudo lsof -iUDP:1194
4) 원복이 안 되는 경우
UFW 규칙 번호를 지정하여 삭제

bash
복사
편집
sudo ufw status numbered
sudo ufw delete <번호>

yaml
복사
편집

---
