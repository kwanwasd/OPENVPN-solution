# VPN 접속 장애 대응 매뉴얼 (OpenVPN)

현장에서 **무슨 일이 발생했고, 어떻게 해결할지**만 빠르게 보도록 정리한 실전 가이드입니다.  
PDF 배포용 원문을 Markdown으로 재구성했고, 스크린샷은 `images/` 폴더에 추가해서 링크하면 됩니다.

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
