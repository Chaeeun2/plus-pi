# PLUS Marketing Design System

이 문서는 현재 운영 중인 `plus-web-marketing` 자산카드 버전의 실제 구성만 정리합니다.

- GitHub: [wani3000/plus-web-marketing](https://github.com/wani3000/plus-web-marketing)
- 로컬 경로: `/Users/hanwha/Documents/GitHub/plus-web-marketing`
- 프로덕션: [plus-web-marketing.vercel.app](https://plus-web-marketing.vercel.app)

이 문서는 `plus-web-marketing_original`이나 다른 히어로 변형을 다루지 않습니다.

## 원칙

- 현재 시각 결과를 바꾸지 않습니다.
- `ds-*`는 반복되는 공통 패턴만 담당합니다.
- 섹션 전용 레이아웃은 `mobile-*` 계열 클래스에서 유지합니다.
- 레이아웃 추상화보다 실제 사용 중인 코드 유지가 우선입니다.

## 1. 프리미티브

### `ds-button`

공통 CTA 버튼 프리미티브입니다.

- 현재 변형: `ds-button--solid`
- 사용 위치:
  - 헤더 `앱 다운로드`
  - 참여 방법 CTA

### `ds-chip`

둥근 배지 프리미티브입니다.

- 현재 변형:
  - `ds-chip--brand`
  - `ds-chip--neutral`
  - `ds-chip--soft-pink`
- 사용 위치:
  - 이벤트 배지
  - 참여 방법 STEP 배지
  - 인사이트 배지

### `ds-heading`

타이틀 프리미티브입니다.

- 현재 변형:
  - `ds-heading--hero`
  - `ds-heading--section`
  - `ds-heading--card`
- 사용 위치:
  - 히어로 타이틀
  - 섹션 타이틀
  - 카드 타이틀

### `ds-copy`

본문 프리미티브입니다.

- 현재 변형:
  - `ds-copy--section`
  - `ds-copy--body`
- 사용 위치:
  - 섹션 설명
  - 보조 카피

## 2. 토큰

### 컬러

컬러는 [styles/plus-colors.css](/Users/hanwha/Documents/GitHub/plus-web-marketing/styles/plus-colors.css)에서 CSS 변수로 관리합니다.

대표 토큰:

- `--color-gray-*`
- `--color-orange-*`
- `--color-bg-*`
- `--color-text-*`
- `--color-border-*`

### 타이포

타이포는 [styles/plus-typography.css](/Users/hanwha/Documents/GitHub/plus-web-marketing/styles/plus-typography.css)에서 관리합니다.

- 기본 텍스트: Pretendard
- 포인트 타이틀: Lifeplus
- 두 폰트 모두 로컬 에셋으로 번들링

텍스트 유틸리티는 `.text-body-*`, `.text-label-*`, `.text-caption-*` 형태로 사용합니다.

## 3. 핵심 섹션

### 헤더

- 핵심 클래스:
  - `mobile-header`
  - `mobile-header__stores`
  - `mobile-header__download`
  - `store-button`
- 동작:
  - 모바일은 직접 스토어 이동
  - 태블릿/데스크톱은 QR 모달 사용

### 히어로

이 저장소를 식별하는 핵심 섹션입니다.

- 핵심 클래스:
  - `mobile-hero`
  - `mobile-hero__sticky-content`
  - `mobile-hero__card-flow`
  - `mobile-overview__card`
  - `mobile-overview__tax-box--large`
  - `mobile-overview__portfolio-box`
- 특징:
  - 자산카드 버전
  - `증여세 신고 금액` 카드 포함
  - `우리 아이 자산` 카드 포함

### 섹션 2: 생애 필수 증여+투자 패키지 신청 이벤트

- 핵심 클래스:
  - `mobile-overview`
  - `mobile-overview__headline`
  - `mobile-overview__description`
  - `mobile-overview__package-panel`
  - `mobile-overview__package-list`
  - `mobile-overview__package-overlay`
- 현재 동작:
  - 모바일: 카피 후 리스트 reveal
  - 태블릿: 간격과 그라데이션을 최종 승자 블록에서 제어
  - 데스크톱: 좌측 카피 먼저, 우측 패널 다음, 이후 캐러셀 시작

### 이벤트

- 핵심 클래스:
  - `mobile-event`
  - `mobile-event__timeline`
  - `mobile-event__step`
  - `mobile-event__gift`
- 특징:
  - sticky 타이틀과 라인이 JS 계산에 연결됨

### 참여 방법

- 핵심 클래스:
  - `mobile-participation`
  - `mobile-participation__step`
  - `mobile-participation__visual`
  - `mobile-participation__alerts-card`
- 특징:
  - STEP 4 알림 카드 포함
  - 토글 체크 애니메이션은 JS 제어

### 인사이트

- 핵심 클래스:
  - `mobile-insight`
  - `mobile-insight__title`
  - `mobile-insight__description`
  - `mobile-insight__video`

### 안내문 / 푸터 / 하단 프로모

- 핵심 클래스:
  - `mobile-guide`
  - `mobile-footer`
  - `site-footer__desktop`
  - `mobile-bottom-promo`

## 4. 인터랙션 컴포넌트

### 스토어 모달

- 상태 클래스: `.store-modal.is-open`
- 책임:
  - QR 표시
  - 포커스 이동
  - ESC / dimmed close
  - 로컬 `qrcode.min.js` 사용

### 섹션 2 패키지 캐러셀

- 책임:
  - 리스트 자동 이동
  - 강조 아이템 오버레이 처리
  - 데스크톱 시퀀스 시작 후 자동 재생

### STEP 4 알림 카드

- 책임:
  - 토글 체크 애니메이션
  - 동의 상태 애니메이션

### 소셜 앱 딥링크

- 책임:
  - 모바일에서 앱 스킴 우선 시도
  - 실패 시 웹 fallback

## 5. 수정 규칙

### 안전한 수정

- 문구만 바뀌면 `index.html`만 수정
- 공통 타이포/버튼/칩 패턴만 `ds-*`에서 수정
- 실제 HTML에 없는 CSS/JS만 제거
- no-op 함수만 제거

### 위험한 수정

- 히어로 구조 자체를 다른 버전 기준으로 바꾸는 작업
- 태블릿/데스크톱 미디어쿼리 전체 병합
- 스크립트를 외부 파일로 분리하면서 DOM 타이밍을 바꾸는 작업
- reveal 순서를 추정으로 변경하는 작업

## 6. 확인 기준

작업 후 최소 아래를 다시 봐야 합니다.

- 모바일 `375`
- 태블릿 `820`
- 데스크톱 `1440`

특히 필수 확인 항목:

- 히어로 자산카드 위치와 스케일
- 섹션 2 리스트 reveal 순서
- 섹션 2 태블릿 간격과 상하 패딩
- 데스크톱 섹션 2 순차 애니메이션
- STEP 4 카드 크기와 배치
- 스토어 QR 모달 동작
