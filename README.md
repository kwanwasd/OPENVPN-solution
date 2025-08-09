# VPN 접속 장애 대응 매뉴얼 (OpenVPN)

본 문서는 VPN 접속 장애가 발생했을 때 현장에서 바로 따라 할 수 있는 최소 절차를 간단히
안내합니다. 원격 근무자·지점·공용망 등 환경 편차가 큰 상황에서 IT 보안 기술지원 엔지니어가
신속히 원인 파악→조치→검증하여 복구 시간을 줄이도록 돕는 것이 목적입니다. ‘무슨 일이
일어났는지’와 ‘어떻게 해결하는지’만 체크리스트 형태로 제공합니다.

## 빠른 시작 (First Response)
- 인터넷 연결/시간(NTP)/보안제품(EDR·방화벽) 변화부터 확인
- 접속점: `remote <호스트/IP> <포트> <프로토콜>` (예: `remote vpn.company.com 1194 udp`)
- 다른 망(테더링)에서 재시도 → 망/ISP 차단 분리
- 상세 절차는 [`docs/index.md`](docs/index.md) 참고

## 리포 구조
```
vpn-troubleshooting-guide/
├─ README.md
├─ docs/
│  ├─ index.md          # 개요·체크리스트·흐름
│  ├─ logs.md           # 재현 & 로그 수집
│  ├─ analysis.md       # 주요 원인 판별
│  ├─ fix.md            # 해결 절차
│  ├─ verify.md         # 해결 확인
│  └─ appendix.md       # 치트시트/템플릿
├─ images/              # 스크린샷(여기에 추가)
└─ .github/workflows/pages.yml  # GitHub Pages 배포(옵션)
```

## 라이선스
MIT (원하면 변경 가능)
