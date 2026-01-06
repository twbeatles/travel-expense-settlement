# 총무의 계산기 (Travel Expense Settlement)

해외여행 경비를 다중 통화로 정확하게 정산하는 웹 애플리케이션입니다.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![React](https://img.shields.io/badge/React-19.2-61dafb.svg)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178c6.svg)
![Vite](https://img.shields.io/badge/Vite-7.2-646cff.svg)

---

## ✨ 주요 기능

### 📊 경비 관리
- **다중 통화 지원**: KRW, USD, EUR, JPY, CNY, THB, VND, PHP
- **실시간 환율 API 연동**: Frankfurter API를 통한 자동 환율 업데이트 (24시간 캐싱)
- **카테고리별 분류**: 식비, 교통, 숙박, 활동, 쇼핑, 기타
- **영수증 OCR**: Tesseract.js를 통한 영수증 자동 인식
- **필터 및 검색**: 날짜, 카테고리, 결제자별 필터링

### 💰 정산 기능
- **자동 정산 계산**: 최소 거래 횟수로 정산 최적화
- **정산 완료 표시**: 완료된 정산 시각적 구분 (체크마크 + 배경색)
- **QR 코드 생성**: 송금 정보 QR 코드
- **리마인더 알림**: Web Notification API 연동
- **PDF/이미지 내보내기**: 정산 결과 공유

### 📈 분석 & 통계 (Dashboard)
- **차트 시각화**: Chart.js 기반 인터랙티브 차트
- **카테고리별 지출 분석** (도넛 차트)
- **일별/인원별 지출 통계** (라인/바 차트)
- **예산 설정 및 모니터링**

### 📅 일정 관리
- **달력 뷰**: 날짜별 지출 시각화
- **예약 지출 기능**: 예정된 지출 미리 등록
- **반복 지출 설정**: 일별/주별/월별 반복

### 📤 데이터 관리
- **CSV/Excel 내보내기**
- **CSV 가져오기**
- **PDF 내보내기**
- **로컬 JSON 백업/복원**

### 🌍 다국어 지원
- 한국어 (기본)
- English
- 日本語
- 中文

### ♿ 접근성
- 스크린 리더 지원 (ARIA)
- 키보드 네비게이션
- 고대비 모드
- 동작 감소 모드 (`prefers-reduced-motion` 지원)
- 최소 터치 타겟 크기 (44px)

---

## 🚀 시작하기

### 요구사항
- Node.js 18+
- npm 또는 yarn

### 설치

```bash
# 저장소 클론
git clone https://github.com/your-repo/travel-expense-settlement.git
cd travel-expense-settlement

# 의존성 설치
npm install

# 개발 서버 실행
npm run dev
```

### 빌드

```bash
# 프로덕션 빌드
npm run build

# 빌드 결과 미리보기
npm run preview
```

### 테스트

```bash
# E2E 테스트 (Playwright)
npx playwright test

# 타입 체크
npx tsc --noEmit
```

---

## 🛠️ 기술 스택

| 카테고리 | 기술 |
|---------|------|
| **프레임워크** | React 19.2, TypeScript 5.9 |
| **빌드 도구** | Vite 7.2 |
| **상태 관리** | Custom Hooks (useTripStore, useDemoTripStore) |
| **백엔드** | Firebase (Auth, Firestore, Storage) |
| **차트** | Chart.js, react-chartjs-2 |
| **PDF** | jsPDF, html2canvas |
| **OCR** | Tesseract.js |
| **QR 코드** | qrcode.react |
| **테스트** | Playwright |

---

## 📁 프로젝트 구조

```
src/
├── components/          # React 컴포넌트
│   ├── common/         # 공통 컴포넌트 (Toast, ErrorBoundary 등)
│   ├── ExpenseTab.tsx  # 지출 탭
│   ├── SettlementTab.tsx # 정산 탭
│   ├── DashboardTab.tsx # 통계 대시보드
│   ├── ParticipantTab.tsx # 참여자 관리
│   └── ...
├── contexts/           # React Context (Auth, Trip, Theme, Demo)
├── hooks/              # 커스텀 훅
│   ├── useTripStore.ts      # Firebase 모드 상태 관리
│   ├── useDemoTripStore.ts  # 데모 모드 상태 관리
│   ├── useExchangeRateAPI.ts # 환율 API
│   ├── useExpenseManagement.ts # 지출 관리
│   └── ...
├── lib/               # 유틸리티 라이브러리
│   ├── firebase.ts    # Firebase 설정
│   ├── i18n.ts        # 다국어 지원
│   └── demoStore.ts   # 데모 데이터 관리
├── constants.ts       # 중앙화된 상수 (THRESHOLDS, STORAGE_KEYS 등)
├── types.ts           # TypeScript 타입 정의
├── index.css          # 글로벌 스타일 (CSS Variables, 다크모드)
├── App.css            # 앱 레이아웃 스타일
└── App.tsx            # 메인 앱 컴포넌트
```

---

## 🎮 사용 모드

### 데모 모드
Firebase 설정 없이 로컬 스토리지를 사용하여 앱의 모든 기능을 체험할 수 있습니다.
- 샘플 여행 데이터 포함
- 모든 기능 동일하게 작동
- 브라우저 새로고침 시에도 데이터 유지

### Firebase 모드
`.env` 파일에 Firebase 설정을 추가하면 실시간 동기화 및 멀티 디바이스 지원이 가능합니다.

```env
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_auth_domain
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_storage_bucket
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id
```

---

## 🎨 UI/UX 특징

### 디자인 시스템
- **CSS Variables**: 일관된 색상, 그림자, 반경 관리
- **다크 모드**: 시스템 설정 자동 감지 + 수동 토글
- **Glassmorphism**: 반투명 배경 + blur 효과
- **마이크로 애니메이션**: 부드러운 전환 효과

### 헤더 UI
- 버튼에 CSS 기반 tooltip (hover 시 표시)
- 적절한 간격으로 터치 오류 방지

### 정산 탭
- 완료된 정산 항목: 체크마크 + 녹색 배경
- "세부보기" 버튼: subtle 밑줄 링크 스타일

### 모달
- Backdrop blur 효과
- Scale-in 애니메이션

---

## 📱 반응형 디자인

- **모바일** (320px - 480px): 터치 친화적 UI, 세로 레이아웃
- **태블릿** (481px - 768px): 2열 그리드 레이아웃
- **데스크톱** (769px+): 호버 효과 및 확장 UI

---

## 🔒 보안

- Division by Zero 방지 (safeDivide 함수)
- NaN/Infinity 체크
- X-Content-Type-Options: nosniff
- X-Frame-Options: SAMEORIGIN
- Firebase Security Rules

---

## 📝 라이선스

MIT License

---

## 🤝 기여

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📧 문의

문의사항이 있으시면 이슈를 생성해 주세요.
