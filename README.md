# VN Office 인사·출장 관리

베트남 오피스(52명)의 근태 관리와 SCM 팀(12명)의 출장 tracking 을 위한 웹 도구.

**🌐 라이브 사이트**: https://sangis389.github.io/SCM-HR-Biz-Trip/

## 기능

- **대시보드**: KPI 5종, 이상 징후, 진행 출장, ROI
- **인원**: VN Office 52명 관리 · 부서 필터
- **근태**: 4,075건 (2026-03 ~ 2026-06) · 부서/월/상태 3중 필터 · 엑셀 임포트
- **SCM 출장**: 5-컬럼 칸반 · 파트너 리스트 · 결과 보고 · ROI
- **리포트**: 부서별/월별/인원별 통계 (순수 CSS/SVG 차트)

## 파일 구조

```
├── index.html          # 앱 진입점
├── app.js              # 애플리케이션 로직
├── styles.css          # 스타일
├── data.json           # 초기 시드 데이터 (근태+출장)
├── .github/
│   └── workflows/
│       └── pages.yml   # GitHub Pages 자동 배포
└── README.md
```

## 로컬 실행

파일들을 로컬 폴더에 두고 `index.html` 을 브라우저에서 열면 됩니다.  
단, `fetch("data.json")` 이 `file://` 프로토콜에서 CORS 오류가 날 수 있으므로 간단한 로컬 서버 권장:

```bash
# Python
python -m http.server 8000

# Node
npx serve
```

접속: http://localhost:8000

## 데이터 저장

- 브라우저 **localStorage** 에 저장 (각 사용자의 브라우저에만 남음)
- 새로고침해도 유지
- `데이터 초기화` 버튼으로 서버의 `data.json` 으로 리셋
- `전체 백업 (JSON)` 으로 언제든 백업 다운로드

## 엑셀 임포트

- **근태**: 근태 화면 상단 드래그 존에 KEYWATCH 형식 xlsx 드롭 → 자동 파싱
- **출장 계획서**: SCM 출장 화면 드래그 존에 Plan/Expense/Report 시트 포함 xlsx 드롭 → 자동 파싱

## 라이선스

MIT
