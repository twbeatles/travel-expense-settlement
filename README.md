# 총무의 계산기 (Travel Expense Settlement)

해외여행 경비를 다중 통화로 정확하게 정산하는 프리미엄 웹 애플리케이션입니다.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![React](https://img.shields.io/badge/React-19.2-61dafb.svg)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178c6.svg)
![Vite](https://img.shields.io/badge/Vite-7.2-646cff.svg)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-3.4-38B2AC.svg)

---

## 📖 목차

- [주요 기능](#-주요-기능)
- [스크린샷](#-스크린샷)
- [시작하기](#-시작하기)
- [사용 방법](#-사용-방법)
- [기술 스택](#%EF%B8%8F-기술-스택)
- [프로젝트 구조](#-프로젝트-구조)
- [환경 설정](#-환경-설정)
- [배포](#-배포)
- [기여](#-기여)

---

## ✨ 주요 기능

### 📊 경비 관리
| 기능 | 설명 |
|-----|-----|
| **다중 통화 지원** | KRW, USD, EUR, JPY, CNY, THB, VND, PHP 8개 통화 |
| **실시간 환율** | Frankfurter API 연동, 24시간 캐싱, 자동 갱신 |
| **영수증 OCR** | Tesseract.js 기반 영수증 자동 인식 |
| **빠른 지출 등록** | 카메라 촬영 → OCR → 자동 입력 |
| **음성 입력** | 한국어 음성으로 지출 내역 등록 |
| **커스텀 카테고리** | 기본 6개 + 사용자 정의 카테고리 |
| **태그 시스템** | 지출 항목에 태그 추가 및 필터링 |
| **영수증 갤러리** | 업로드된 영수증 모아보기 |

### 💰 정산 기능
| 기능 | 설명 |
|-----|-----|
| **자동 최적화 정산** | 최소 거래 횟수 알고리즘 |
| **부분 정산** | 일부 금액만 먼저 정산 처리 |
| **정산 완료 표시** | 체크마크 + 시각적 구분 |
| **QR 코드 생성** | 송금 정보 QR 코드 생성 |
| **정산 메시지** | 템플릿 기반 메시지 생성 (친근한/공식적/짧은) |
| **마감일 설정** | D-day 카운트다운, 리마인더 알림 |
| **결제 딥링크** | 카카오페이, 토스 바로 결제 링크 |

### 📈 분석 & 통계
| 기능 | 설명 |
|-----|-----|
| **카테고리별 분석** | 도넛 차트로 지출 분포 확인 |
| **일별 지출 추이** | 라인 차트로 일별 트렌드 확인 |
| **인원별 지출** | 바 차트로 개인별 지출 비교 |
| **예산 모니터링** | 설정 예산 대비 사용률 표시 |
| **고급 분석** | 트렌드 분석, 예산 예측, 통화별 분석 |

### 👥 그룹 & 협업
| 기능 | 설명 |
|-----|-----|
| **초대 코드** | 6자리 코드로 여행에 참여 |
| **실시간 동기화** | Firebase 기반 멀티 디바이스 동기화 |
| **서브 그룹** | 여행 내 소그룹별 정산 |
| **역할 권한** | 총무/참여자/게스트 권한 분리 |
| **실시간 알림** | 다른 사용자 활동 알림 |
| **오프라인 지원** | 오프라인 작업 후 자동 동기화 |

### 📅 여행 계획
| 기능 | 설명 |
|-----|-----|
| **타임라인 일정** | 날짜별 활동/숙소/교통 계획 |
| **체크리스트** | 카테고리별 여행 준비물 관리 |
| **여행 템플릿** | 자주 가는 여행지 템플릿 저장 |
| **날씨 정보** | 여행지 날씨 확인 |
| **위치 태그** | 지출 항목에 위치 정보 추가 |

### 📤 데이터 관리
| 기능 | 설명 |
|-----|-----|
| **CSV 내보내기** | 지출 내역 스프레드시트 변환 |
| **PDF 보고서** | 정산 결과 PDF 다운로드 |
| **CSV 가져오기** | 외부 데이터 일괄 등록 |
| **자동 백업** | 주기적 로컬 백업 |
| **JSON 백업/복원** | 전체 데이터 백업 및 복구 |

### 🌍 다국어 & 접근성
- **4개 언어 지원**: 한국어, English, 日本語, 中文
- **다크 모드**: 시스템 설정 자동 감지 + 수동 토글
- **스크린 리더 지원**: ARIA 라벨 완비
- **키보드 네비게이션**: 마우스 없이 전체 기능 사용
- **고대비/동작 감소 모드**: 시스템 설정 연동

---

## 📸 스크린샷

> 추후 스크린샷 추가 예정

---

## 🚀 시작하기

### 시스템 요구사항
- **Node.js**: 20.19+ 또는 22.12+
- **npm**: 10+ 또는 **yarn**: 1.22+
- **브라우저**: Chrome 90+, Firefox 90+, Safari 15+, Edge 90+

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

개발 서버가 `http://localhost:5173`에서 시작됩니다.

### 빌드 및 배포

```bash
# 프로덕션 빌드
npm run build

# 빌드 결과 미리보기
npm run preview

# 타입 검사
npx tsc --noEmit

# E2E 테스트
npx playwright test
```

---

## 📖 사용 방법

### 1️⃣ 시작하기

#### 데모 모드 (Firebase 설정 없이)
1. 앱 실행 시 **"데모 모드로 체험하기"** 버튼 클릭
2. 샘플 여행 데이터로 모든 기능 체험
3. 데이터는 브라우저 로컬 스토리지에 저장

#### Firebase 모드 (실시간 동기화)
1. Firebase 프로젝트 생성 및 `.env` 파일 설정
2. Google 로그인으로 인증
3. 여행 생성 또는 초대 코드로 참여

### 2️⃣ 여행 생성

```
1. "새 여행 만들기" 버튼 클릭
2. 여행 이름 입력 (예: "일본 오사카 여행")
3. 시작일/종료일 설정 (선택)
4. 예산 설정 (선택)
5. "만들기" 버튼 클릭
```

### 3️⃣ 참여자 관리

```
[참여자] 탭에서:
1. 참여자 이름 입력 후 "추가" 버튼 클릭
2. 참여자 클릭 → 상세 정보 편집
   - 은행 계좌 정보
   - 카카오페이/토스 ID
   - 결제 수단 등록
3. 드래그 앤 드롭으로 순서 변경
```

### 4️⃣ 지출 등록

#### 기본 등록
```
[지출] 탭에서:
1. "지출 추가" 버튼 클릭
2. 필수 정보 입력:
   - 설명 (예: "점심 라멘")
   - 금액 (예: 1200)
   - 통화 선택 (예: JPY)
   - 결제자 선택
   - 분담자 선택 (전체선택 가능)
3. 선택 정보:
   - 카테고리
   - 날짜
   - 영수증 사진
   - 태그
4. "추가" 버튼 클릭
```

#### 빠른 등록 (영수증 OCR)
```
1. 우측 하단 카메라 버튼 클릭
2. 영수증 촬영 또는 사진 선택
3. OCR 자동 인식 결과 확인
4. 필요시 수정 후 등록
```

#### 음성 입력
```
1. 마이크 버튼 클릭
2. "점심 라멘 천이백엔" 음성 입력
3. 자동 파싱된 결과 확인 후 등록
```

### 5️⃣ 정산 확인

```
[정산] 탭에서:
1. 자동 계산된 정산 목록 확인
   - 누가 → 누구에게 → 얼마
2. 정산 완료 시 "완료" 버튼 클릭
3. 부분 정산 시 금액 입력 후 처리
4. QR 코드 또는 결제 링크로 송금
```

### 6️⃣ 통계 확인

```
[통계] 탭에서:
1. 카테고리별 지출 비율 (도넛 차트)
2. 일별 지출 추이 (라인 차트)
3. 인원별 지출 비교 (바 차트)
4. 예산 대비 사용률
5. 기간 필터 (오늘/이번 주/이번 달/전체)
```

### 7️⃣ 데이터 내보내기

```
설정 → 데이터 관리:
- CSV 내보내기: 엑셀에서 열기 가능
- PDF 내보내기: 정산 보고서 생성
- JSON 백업: 전체 데이터 백업 파일
```

---

## 🎮 사용 모드 비교

| 기능 | 데모 모드 | Firebase 모드 |
|-----|----------|--------------|
| 데이터 저장 | 로컬 스토리지 | Firebase Firestore |
| 멀티 디바이스 | ❌ | ✅ |
| 실시간 동기화 | ❌ | ✅ |
| 초대 코드 공유 | 로컬 전용 | 온라인 공유 |
| 영수증 업로드 | 로컬 URL | Firebase Storage |
| 로그인 필요 | ❌ | ✅ (Google) |

---

## 🛠️ 기술 스택

| 카테고리 | 기술 |
|---------|------|
| **프레임워크** | React 19.2, TypeScript 5.9 |
| **빌드 도구** | Vite 7.2 |
| **상태 관리** | Custom Hooks + Zustand |
| **백엔드** | Firebase (Auth, Firestore, Storage) |
| **오프라인** | IndexedDB + Service Worker |
| **스타일링** | Tailwind CSS, CSS Modules |
| **차트** | Chart.js, react-chartjs-2 |
| **PDF** | jsPDF, html2canvas |
| **OCR** | Tesseract.js |
| **QR 코드** | qrcode.react |
| **국제화** | Custom i18n (ko/en/ja/zh) |
| **테스트** | Playwright |

---

## 📁 프로젝트 구조

```
src/
├── components/         # 134+ React 컴포넌트
│   ├── common/         # 공통 (Toast, ErrorBoundary, Modal)
│   ├── ui/             # 공통 UI 컴포넌트 (Button, Input, Modal 등)
│   ├── ExpenseTab.tsx       # 지출 관리 탭
│   ├── SettlementTab.tsx    # 정산 탭
│   ├── DashboardTab.tsx     # 통계 대시보드
│   ├── ParticipantTab.tsx   # 참여자 관리
│   ├── ReceiptGallery.tsx   # 영수증 갤러리
│   ├── VoiceExpenseInput.tsx # 음성 입력
│   └── ...
├── contexts/           # React Context
│   ├── AuthContext.tsx      # 인증 상태
│   ├── TripContext.tsx      # 여행 상태
│   ├── ThemeContext.tsx     # 테마 (다크모드)
│   └── DemoContext.tsx      # 데모 모드
├── hooks/              # 29개 커스텀 훅
│   ├── useTripStore.ts      # Firebase 데이터 관리
│   ├── useDemoTripStore.ts  # 데모 데이터 관리
│   ├── useOfflineSync.tsx   # 오프라인 동기화
│   ├── useExchangeRateAPI.ts # 환율 API
│   ├── useOCR.ts            # 영수증 OCR
│   ├── useSpeechInput.ts    # 음성 입력
│   └── ...
├── lib/                # 외부 서비스 연동
│   ├── firebase.ts          # Firebase 설정
│   ├── i18n.tsx             # 다국어 시스템
│   └── demoStore.ts         # 데모 데이터 저장소
├── utils/              # 유틸리티 함수
│   ├── settlementCalculator.ts  # 정산 알고리즘
│   ├── validation.ts        # 입력값 검증
│   ├── formatting.ts        # 포맷팅
│   └── logger.ts            # 로깅
├── constants.ts        # 상수 정의
├── types.ts            # TypeScript 타입
└── App.tsx             # 앱 진입점
```

---

## ⚙️ 환경 설정

### Firebase 설정 (선택)

`.env` 파일 생성:

```env
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=123456789
VITE_FIREBASE_APP_ID=1:123456789:web:abcdef
```

### Firebase 콘솔 설정

1. [Firebase 콘솔](https://console.firebase.google.com) 접속
2. 새 프로젝트 생성
3. Authentication → Google 로그인 활성화
4. Firestore Database 생성 (아시아 리전 권장)
5. Storage 활성화
6. 웹 앱 추가 → 설정값을 `.env`에 복사

---

## 🚢 배포

### GitHub Pages (무료)

```bash
# 빌드 및 배포
npm run build
npx gh-pages -d dist
```

또는 GitHub Actions 자동 배포 설정:

1. `.github/workflows/deploy.yml` 생성
2. Settings → Pages → Source: "GitHub Actions" 선택

### Vercel / Netlify

```bash
# Vercel
npx vercel

# Netlify
npx netlify deploy --prod --dir=dist
```

---

## 🔒 보안

- **입력값 검증**: 모든 사용자 입력 sanitization
- **안전한 계산**: `safeDivide` 함수로 0 나눗셈 방지
- **Firebase Security Rules**: 인가된 사용자만 데이터 접근
- **XSS 방지**: DOMPurify로 HTML sanitization
- **파일 크기 제한**: 영수증 10MB, CSV 5MB

---

## 📝 라이선스

MIT License - 자유롭게 사용, 수정, 배포 가능합니다.

---

## 🤝 기여

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### 코드 스타일
- TypeScript strict mode
- ESLint + Prettier
- 한글 주석 권장

---

## 📧 문의

문의사항이 있으시면 [Issues](https://github.com/your-repo/travel-expense-settlement/issues)를 생성해 주세요.
