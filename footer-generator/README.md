# Footer Generator

웹페이지용 푸터 컴포넌트 자동 생성 스킬

## 두 가지 생성 모드

### Mode 1: 공통 푸터 제작 ⚡
기본 회사 정보(두온교육(주) × 미래이음연구소)로 빠르게 생성

**사용 시나리오:**
- 회사 공식 프로젝트
- 일관된 정보 유지 필요
- 빠른 생성 원함

**트리거 키워드:**
```
"공통 푸터 만들어줘"
"기본 푸터 생성"
"회사 푸터 추가"
```

### Mode 2: 맞춤 푸터 제작 🎨
사용자가 제공한 정보로 맞춤형 푸터 생성

**사용 시나리오:**
- 다른 회사/클라이언트 프로젝트
- 개인 포트폴리오
- 커스터마이징 필요

**트리거 키워드:**
```
"맞춤 푸터 만들어줘"
"커스텀 푸터 생성"
"내 정보로 푸터 만들기"
```

## 사용 방법

### 자동 활성화

다음 키워드를 사용하면 자동으로 스킬이 활성화됩니다:

```
# Mode 1 (공통 푸터)
- "공통 푸터 만들어줘"
- "기본 푸터 생성"
- "회사 푸터 추가"

# Mode 2 (맞춤 푸터)
- "맞춤 푸터 만들어줘"
- "커스텀 푸터 생성"
- "내 정보로 푸터"
```

### 수동 활성화

```bash
/footer-generator
```

## 포함된 정보

### 기본 정보
- 회사명: 두온교육(주) × 미래이음연구소
- 대표전화: 070-5089-5960
- 연락처: 010-3343-4000
- 사업자등록번호: 264-87-01676
- 통신판매업신고번호: 2020-경기평택-0204

### 연락처
- 이메일: duonedu@duonedu.net
- 웹사이트: https://www.duonedu.info
- 주소: 경기도 평택시 고덕중앙로 322 704호

### 입금 정보
- 무통장 입금: 1005-903-896511 우리은행
- 예금주: 두온교육(주)

### 소셜 미디어
- 유튜브: https://www.youtube.com/@mintorain7
- 인스타그램: https://www.instagram.com/mintorain/
- 페이스북: https://www.facebook.com/mintorain
- X (Twitter): https://x.com/mintorain7
- 카카오톡 오픈채팅: https://open.kakao.com/o/gpLP613g
- 고객센터: http://pf.kakao.com/_UzjZG/chat
- 홈페이지: https://mintorain-webapp.pages.dev/

## 출력 형식

### 1. React Component (기본)
```jsx
import Footer from './components/Footer';

export default function App() {
  return (
    <div>
      {/* 페이지 콘텐츠 */}
      <Footer />
    </div>
  );
}
```

### 2. HTML + Tailwind CSS
```html
<!DOCTYPE html>
<html>
<body>
  <!-- 페이지 콘텐츠 -->

  <!-- Footer -->
  <footer class="bg-gray-50 border-t border-gray-200 py-12 px-6">
    <!-- ... -->
  </footer>
</body>
</html>
```

### 3. Vue Component
```vue
<template>
  <div>
    <!-- 페이지 콘텐츠 -->
    <Footer />
  </div>
</template>

<script setup>
import Footer from './components/Footer.vue';
</script>
```

## 스타일 변형

### Minimal (간단한 버전)
- 기본 정보만 포함
- 한 줄 레이아웃
- 작은 사이즈

### Dark Theme (다크 테마)
- 검은색 배경
- 흰색 텍스트
- 블루 강조색

### Full (전체 버전, 기본값)
- 모든 정보 포함
- 3단 그리드 레이아웃
- 상세한 연락처 및 소셜 미디어

## 사용 예제

### Mode 1: 공통 푸터 제작

```bash
# React 컴포넌트 (기본 정보 자동 사용)
"공통 푸터 만들어줘, React로"

# HTML 버전
"기본 푸터 생성, HTML 형식으로"

# Vue 컴포넌트
"회사 푸터 추가, Vue로"

# 다크 테마
"공통 푸터 다크 테마로"

# 미니멀 버전
"간단한 회사 푸터만"
```

### Mode 2: 맞춤 푸터 제작

```bash
# 예시 1: 기본 맞춤 푸터
"맞춤 푸터 만들어줘, React로
회사명: ABC Corporation
이메일: contact@abc.com
전화: 02-1234-5678"

# 예시 2: 상세 맞춤 푸터
"커스텀 푸터 생성, HTML로
회사명: XYZ Studio
이메일: hello@xyz.studio
전화: 010-9876-5432
주소: 서울시 강남구 테헤란로 123
사업자등록번호: 123-45-67890
소셜: 인스타그램 @xyzstudio, 페이스북 facebook.com/xyz
웹사이트: https://xyz.studio"

# 예시 3: 미니멀 맞춤 푸터
"간단한 맞춤 푸터, Vue로
회사명: My Portfolio
이메일: me@portfolio.com"

# 예시 4: 입금 정보 포함
"맞춤 푸터 만들기
회사명: 온라인샵
이메일: shop@example.com
전화: 02-1111-2222
계좌: 123-456-789012 국민은행, 예금주: 온라인샵"
```

### 맞춤 푸터 생성 시 제공 가능한 정보

**필수:**
- 회사명/프로젝트명
- 이메일 또는 전화번호

**선택:**
- 주소
- 사업자등록번호
- 통신판매업신고번호
- 소셜 미디어 (인스타그램, 페이스북, 유튜브, X 등)
- 웹사이트 URL
- 입금 계좌 정보
- 고객센터 링크

## 커스터마이징

스킬 파일(`SKILL.md`)을 수정하여 다음을 변경할 수 있습니다:

- 회사 정보
- 연락처
- 소셜 미디어 링크
- 디자인 스타일
- 색상 테마

## 파일 위치

```
C:\Users\minto\.claude\skills\footer-generator\
├── SKILL.md      # 스킬 정의 파일
└── README.md     # 이 파일
```
