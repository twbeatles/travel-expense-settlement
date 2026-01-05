# 총무의 계산기 (Travel Expense Settlement)

여행 경비 정산을 위한 모바일 친화적 웹 앱입니다.

![React](https://img.shields.io/badge/React-18-blue)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue)
![Vite](https://img.shields.io/badge/Vite-7.3-purple)
![Firebase](https://img.shields.io/badge/Firebase-Optional-orange)

## ✨ 주요 기능

### 💰 지출 관리
- 지출 추가/수정/삭제
- 다중 통화 지원 (KRW, USD, EUR, JPY 등)
- 영수증 사진 업로드 및 OCR 자동 인식
- 위치 기반 통화 자동 선택

### 👥 참여자 관리
- 여행 참여자 추가/삭제
- 커스텀 분할 비율 지원
- 초대 코드로 여행 공유

### 📊 정산
- 실시간 잔액 계산
- 최적화된 송금 안내
- 정산 완료 상태 추적

### 🎨 UI/UX
- 다크 모드 지원
- 글래스모피즘 디자인
- 마이크로 애니메이션
- 모바일 최적화 (PWA)

---

## 🚀 시작하기

### 사전 요구 사항
- Node.js 20.19+ 또는 22.12+
- npm 또는 yarn

### 설치

```bash
# 저장소 클론
git clone https://github.com/your-username/travel-expense-settlement.git
cd travel-expense-settlement

# 의존성 설치
npm install

# 개발 서버 실행
npm run dev
```

### 데모 모드
Firebase 설정 없이 데모 모드로 앱을 사용할 수 있습니다.

### Firebase 설정 (선택)
실시간 동기화를 원하면 `.env` 파일을 생성하세요:

```env
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_auth_domain
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_storage_bucket
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id
```

---

## 📦 기술 스택

| 분류 | 기술 |
|------|------|
| 프레임워크 | React 18, TypeScript |
| 빌드 도구 | Vite 7 |
| 상태 관리 | Zustand + Immer |
| 데이터 페칭 | React Query |
| 스타일 | CSS Variables, Glassmorphism |
| 백엔드 | Firebase (선택) |
| OCR | Tesseract.js |
| 테스트 | Playwright |

---

## 📁 프로젝트 구조

```
src/
├── components/          # UI 컴포넌트
│   ├── common/          # 공통 컴포넌트 (Toast, FAB, Skeleton)
│   └── ...
├── contexts/            # React Context
├── hooks/               # 커스텀 훅
├── stores/              # Zustand 스토어
├── lib/                 # 유틸리티 (Firebase, Query Client)
└── types.ts             # TypeScript 타입
```

---

## 🛠️ 스크립트

```bash
npm run dev       # 개발 서버
npm run build     # 프로덕션 빌드
npm run preview   # 빌드 미리보기
npm run lint      # ESLint 검사
```

---

## 📱 PWA 지원

앱을 홈 화면에 추가하여 네이티브 앱처럼 사용할 수 있습니다.

---

## 🔧 최적화

- **코드 스플리팅**: Firebase, OCR, 상태 관리 라이브러리 분리
- **Tree Shaking**: 미사용 코드 자동 제거
- **Lazy Loading**: 필요 시 컴포넌트 로드
- **이미지 최적화**: WebP 형식 지원

---

## 🤝 기여

1. Fork
2. Feature 브랜치 생성 (`git checkout -b feature/amazing`)
3. 커밋 (`git commit -m 'Add amazing feature'`)
4. Push (`git push origin feature/amazing`)
5. Pull Request 생성

---

## 📄 라이선스

MIT License
