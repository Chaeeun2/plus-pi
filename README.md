# PLUS Website Marketing

`plus-web-marketing` 저장소의 현재 운영 버전 문서입니다.

이 프로젝트는 `히어로가 자산카드인 버전`만 관리합니다.

- GitHub: [wani3000/plus-web-marketing](https://github.com/wani3000/plus-web-marketing)
- 로컬 경로: `/Users/hanwha/Documents/GitHub/plus-web-marketing`
- 프로덕션: [plus-web-marketing.vercel.app](https://plus-web-marketing.vercel.app)

아래는 이 저장소의 관리 대상이 아닙니다.

- `plus-web-marketing_original`
- `plus-website-marketing-original`

## 원칙

- 모바일/태블릿/데스크톱의 현재 시각 결과를 유지합니다.
- 디자인이 바뀔 가능성이 있는 구조 변경은 멈추고 먼저 영향 범위를 확인합니다.
- 이 프로젝트는 빌드 없는 정적 사이트이므로 CSS 우선순위와 미디어쿼리 승자 규칙이 중요합니다.

## 실행

정적 파일 서버만 띄우면 됩니다.

```bash
python3 -m http.server 3000 --bind 0.0.0.0
```

- 로컬: `http://localhost:3000`
- 동일 네트워크 모바일 확인: `http://<내IP>:3000`

## 배포

현재 기준 배포 대상은 [plus-web-marketing.vercel.app](https://plus-web-marketing.vercel.app) 입니다.

GitHub `main` 브랜치 푸시 후 Vercel Git 연동으로 프로덕션 배포가 생성됩니다.

직접 배포가 필요하면 일반적으로 아래 명령을 사용합니다.

```bash
vercel --prod --yes
```

## 구조

- 진입 파일: [index.html](/Users/hanwha/Documents/GitHub/plus-web-marketing/index.html)
- 메인 스타일: [styles/globals.css](/Users/hanwha/Documents/GitHub/plus-web-marketing/styles/globals.css)
- 디자인 시스템 프리미티브: [styles/design-system.css](/Users/hanwha/Documents/GitHub/plus-web-marketing/styles/design-system.css)
- 컬러 토큰: [styles/plus-colors.css](/Users/hanwha/Documents/GitHub/plus-web-marketing/styles/plus-colors.css)
- 타이포 토큰: [styles/plus-typography.css](/Users/hanwha/Documents/GitHub/plus-web-marketing/styles/plus-typography.css)
- 디자인 시스템 문서: [DESIGN_SYSTEM.md](/Users/hanwha/Documents/GitHub/plus-web-marketing/DESIGN_SYSTEM.md)
- 에셋: `/Users/hanwha/Documents/GitHub/plus-web-marketing/assets`

## 페이지 구성

현재 프로덕션 기준 섹션 순서는 아래와 같습니다.

1. 헤더
2. 히어로
3. 섹션 2: 생애 필수 증여+투자 패키지 신청 이벤트
4. 이벤트
5. 참여 방법
6. 인사이트
7. 안내문
8. 푸터
9. 하단 프로모

## 히어로 기준

이 저장소의 가장 중요한 식별 포인트는 히어로입니다.

- 상단 타이틀 아래에 자산 관련 카드가 노출됩니다.
- `증여세 신고 금액` 카드와 `우리 아이 자산` 카드가 포함됩니다.
- 즉, 이 저장소는 `이미지 카드 3개 버전`이 아니라 `자산카드 버전`입니다.

## 반응형 기준

- 모바일: `0px ~ 767px`
- 태블릿: `768px ~ 1199px`
- 데스크톱: `1200px+`

반응형 수정 시 항상 모바일 기본값과 태블릿/데스크톱 오버라이드를 같이 확인해야 합니다.

## 인터랙션

현재 인라인 스크립트는 아래 기능을 담당합니다.

- 헤더 높이를 읽어 `--mobile-header-height` 동기화
- 히어로 통과 여부에 따라 `hero-top`, `hero-passed` 클래스 토글
- 모바일 다운로드 버튼 플랫폼 분기
- 태블릿/데스크톱 스토어 버튼 클릭 시 QR 모달 오픈
- 유튜브/인스타 링크의 모바일 앱 스킴 fallback 처리
- 섹션 reveal 애니메이션
- 섹션 2 패키지 리스트 캐러셀
- 데스크톱 섹션 2 순차 애니메이션
- 이벤트 타임라인 sticky/line 계산
- 참여 방법 STEP 4 알림 카드 애니메이션

## 자산 기준

현재 운영 기준 자산 상태는 아래와 같습니다.

- 시각 에셋: 로컬 `assets/`
- Pretendard: 로컬 `assets/fonts/pretendard/`
- Lifeplus: 로컬 `assets/fonts/LIFEPLUS-Bold.ttf`
- QR 생성: 로컬 `assets/vendor/qrcode.min.js`

외부 의존은 목적 링크만 남아 있습니다.

- Google Play
- App Store
- YouTube
- Instagram

## 자주 수정하는 파일

- 문구 변경: [index.html](/Users/hanwha/Documents/GitHub/plus-web-marketing/index.html)
- 시각 수정: [styles/globals.css](/Users/hanwha/Documents/GitHub/plus-web-marketing/styles/globals.css)
- 토큰 수정: [styles/plus-colors.css](/Users/hanwha/Documents/GitHub/plus-web-marketing/styles/plus-colors.css), [styles/plus-typography.css](/Users/hanwha/Documents/GitHub/plus-web-marketing/styles/plus-typography.css)
- 공통 프리미티브 수정: [styles/design-system.css](/Users/hanwha/Documents/GitHub/plus-web-marketing/styles/design-system.css)

## 수정 순서

1. 수정 대상이 어느 섹션인지 확인합니다.
2. 모바일 기본 스타일을 먼저 확인합니다.
3. 태블릿 오버라이드를 확인합니다.
4. 데스크톱 오버라이드를 확인합니다.
5. 해당 DOM을 JS가 제어하는지 확인합니다.
6. 최소 `375 / 820 / 1440` 기준으로 확인합니다.

## 검수 포인트

변경 후 최소 아래 항목은 다시 확인해야 합니다.

- 히어로 자산카드 레이아웃
- 섹션 2 reveal 순서
- 섹션 2 리스트 상하 그라데이션
- 이벤트 sticky 타임라인
- STEP 4 알림 카드
- 스토어 QR 모달
- 하단 프로모 노출/숨김

## 최근 상태

현재 저장소는 아래 상태를 반영하고 있습니다.

- 자산카드 히어로 버전 유지
- Pretendard 로컬화
- QR 생성 로컬화
- 섹션 2 모바일/태블릿/데스크톱 인터랙션 조정 반영
- 이벤트 섹션 카피 및 기프트 라벨 최신 문구 반영
- 특정 브라우저 히어로 우측 흰 여백 방지용 가로 overflow 차단 반영
- 문서 기준을 `plus-web-marketing` 배포와 저장소 기준으로 재정렬
