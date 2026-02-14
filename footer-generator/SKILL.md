---
name: footer-generator
description: Generate footer components with two modes - (1) Common footer using 두온교육(주) × 미래이음연구소 default info, or (2) Custom footer with user-provided content. Supports React, HTML, and Tailwind CSS formats.
---

# Footer Generator

웹페이지용 푸터 컴포넌트를 생성하는 스킬입니다.

## 사용 모드

### Mode 1: 공통 푸터 제작 (Default Company Footer)
기본 회사 정보를 사용하여 자동으로 푸터를 생성합니다.
- **대상**: 두온교육(주) × 미래이음연구소 관련 프로젝트
- **장점**: 빠른 생성, 일관된 정보
- **사용법**: "공통 푸터 만들어줘" 또는 "기본 푸터 생성"

### Mode 2: 맞춤 푸터 제작 (Custom Footer)
사용자가 제공한 정보로 맞춤형 푸터를 생성합니다.
- **대상**: 다른 회사/프로젝트
- **장점**: 유연한 커스터마이징
- **사용법**: "맞춤 푸터 만들어줘" + 필요한 정보 제공

## Default Company Information

### 회사 정보
- **회사명**: 두온교육(주) × 미래이음연구소
- **대표전화**: 070-5089-5960
- **연락처**: 010-3343-4000
- **사업자등록번호**: 264-87-01676
- **통신판매업신고번호**: 2020-경기평택-0204

### 연락처
- **이메일**: duonedu@duonedu.net
- **웹사이트**: https://www.duonedu.info
- **주소**: 경기도 평택시 고덕중앙로 322 704호

### 입금 정보
- **무통장 입금**: 1005-903-896511 우리은행
- **예금주**: 두온교육(주)

### 소셜 미디어 & 링크
- **유튜브**: https://www.youtube.com/@mintorain7
- **인스타그램**: https://www.instagram.com/mintorain/
- **페이스북**: https://www.facebook.com/mintorain
- **X (Twitter)**: https://x.com/mintorain7
- **카카오톡 오픈채팅**: https://open.kakao.com/o/gpLP613g
- **고객센터**: http://pf.kakao.com/_UzjZG/chat
- **홈페이지**: https://mintorain-webapp.pages.dev/

---

## Mode 1: 공통 푸터 제작 (Quick Start)

### 트리거 키워드
```
"공통 푸터 만들어줘"
"기본 푸터 생성"
"회사 푸터 추가"
"두온교육 푸터"
```

### 사용 예시
```bash
# React 컴포넌트
"공통 푸터 만들어줘, React로"

# HTML
"기본 푸터 생성, HTML 형식으로"

# Vue 컴포넌트
"회사 푸터 추가, Vue로"

# 다크 테마
"공통 푸터 다크 테마로"
```

위 명령을 사용하면 **Default Company Information**에 있는 정보로 자동 생성됩니다.

---

## Mode 2: 맞춤 푸터 제작 (Custom Footer)

### 트리거 키워드
```
"맞춤 푸터 만들어줘"
"커스텀 푸터 생성"
"내 정보로 푸터 만들기"
```

### 필요한 정보

사용자가 다음 정보를 제공해야 합니다:

#### 필수 정보
- **회사명/프로젝트명**: (예: "ABC Corp")
- **연락처**: 전화번호, 이메일 등
- **Copyright 정보**: 저작권 표시

#### 선택 정보
- **주소**: 사업장 주소
- **사업자 정보**: 사업자등록번호, 통신판매업신고번호
- **소셜 미디어**: 링크 및 플랫폼 이름
- **추가 링크**: 웹사이트, 고객센터 등
- **입금 정보**: 계좌번호 (필요시)

### 사용 예시

```bash
# 예시 1: 간단한 맞춤 푸터
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
소셜: 인스타그램 @xyzstudio, 페이스북 @xyzstudio
웹사이트: https://xyz.studio"
```

### 맞춤 푸터 생성 프로세스

1. **정보 수집**: 사용자가 제공한 정보를 분석
2. **구조 결정**: 제공된 정보량에 따라 레이아웃 자동 조정
3. **컴포넌트 생성**: 선택한 형식(React/HTML/Vue)으로 생성
4. **스타일 적용**: 요청한 테마(기본/다크/미니멀) 적용

---

## Usage - Mode 1 (Common Footer)

### React Component (Default)

```jsx
// components/Footer.jsx
import React from 'react';

export default function Footer() {
  return (
    <footer className="bg-gray-50 border-t border-gray-200 py-12 px-6">
      <div className="max-w-7xl mx-auto">
        {/* Company Header */}
        <div className="mb-8">
          <h3 className="text-2xl font-bold text-gray-900 mb-4">
            두온교육(주) × 미래이음연구소
          </h3>
        </div>

        {/* Main Content Grid */}
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-8">
          {/* Contact Information */}
          <div>
            <h4 className="font-semibold text-gray-900 mb-3">연락처</h4>
            <ul className="space-y-2 text-sm text-gray-600">
              <li>대표전화: <a href="tel:070-5089-5960" className="hover:text-blue-600">070-5089-5960</a></li>
              <li>연락처: <a href="tel:010-3343-4000" className="hover:text-blue-600">010-3343-4000</a></li>
              <li>이메일: <a href="mailto:duonedu@duonedu.net" className="hover:text-blue-600">duonedu@duonedu.net</a></li>
              <li>웹사이트: <a href="https://www.duonedu.info" target="_blank" rel="noopener noreferrer" className="hover:text-blue-600">www.duonedu.info</a></li>
            </ul>
          </div>

          {/* Business Information */}
          <div>
            <h4 className="font-semibold text-gray-900 mb-3">사업자 정보</h4>
            <ul className="space-y-2 text-sm text-gray-600">
              <li>사업자등록번호: 264-87-01676</li>
              <li>통신판매업신고번호: 2020-경기평택-0204</li>
              <li>주소: 경기도 평택시 고덕중앙로 322 704호</li>
            </ul>
            <div className="mt-4 pt-4 border-t border-gray-200">
              <h5 className="font-semibold text-gray-700 mb-2 text-sm">무통장 입금</h5>
              <p className="text-sm text-gray-600">1005-903-896511 우리은행</p>
              <p className="text-sm text-gray-600">예금주: 두온교육(주)</p>
            </div>
          </div>

          {/* Social Media & Links */}
          <div>
            <h4 className="font-semibold text-gray-900 mb-3">소셜 미디어</h4>
            <ul className="space-y-2 text-sm">
              <li>
                <a href="https://www.youtube.com/@mintorain7" target="_blank" rel="noopener noreferrer" className="text-gray-600 hover:text-red-600 flex items-center gap-2">
                  <span>📺</span> 유튜브
                </a>
              </li>
              <li>
                <a href="https://www.instagram.com/mintorain/" target="_blank" rel="noopener noreferrer" className="text-gray-600 hover:text-pink-600 flex items-center gap-2">
                  <span>📷</span> 인스타그램
                </a>
              </li>
              <li>
                <a href="https://www.facebook.com/mintorain" target="_blank" rel="noopener noreferrer" className="text-gray-600 hover:text-blue-700 flex items-center gap-2">
                  <span>👥</span> 페이스북
                </a>
              </li>
              <li>
                <a href="https://x.com/mintorain7" target="_blank" rel="noopener noreferrer" className="text-gray-600 hover:text-black flex items-center gap-2">
                  <span>𝕏</span> X (Twitter)
                </a>
              </li>
              <li>
                <a href="https://open.kakao.com/o/gpLP613g" target="_blank" rel="noopener noreferrer" className="text-gray-600 hover:text-yellow-500 flex items-center gap-2">
                  <span>💬</span> 카카오톡 오픈채팅
                </a>
              </li>
              <li>
                <a href="http://pf.kakao.com/_UzjZG/chat" target="_blank" rel="noopener noreferrer" className="text-gray-600 hover:text-yellow-500 flex items-center gap-2">
                  <span>🔧</span> 고객센터
                </a>
              </li>
              <li>
                <a href="https://mintorain-webapp.pages.dev/" target="_blank" rel="noopener noreferrer" className="text-gray-600 hover:text-blue-600 flex items-center gap-2">
                  <span>🏠</span> 홈페이지
                </a>
              </li>
            </ul>
          </div>
        </div>

        {/* Copyright */}
        <div className="border-t border-gray-200 pt-6 text-center">
          <p className="text-sm text-gray-500">
            © {new Date().getFullYear()} 두온교육(주) × 미래이음연구소. All rights reserved.
          </p>
        </div>
      </div>
    </footer>
  );
}
```

### Tailwind CSS + HTML

```html
<footer class="bg-gray-50 border-t border-gray-200 py-12 px-6">
  <div class="max-w-7xl mx-auto">
    <!-- Company Header -->
    <div class="mb-8">
      <h3 class="text-2xl font-bold text-gray-900 mb-4">
        두온교육(주) × 미래이음연구소
      </h3>
    </div>

    <!-- Main Content Grid -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-8">
      <!-- Contact Information -->
      <div>
        <h4 class="font-semibold text-gray-900 mb-3">연락처</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li>대표전화: <a href="tel:070-5089-5960" class="hover:text-blue-600">070-5089-5960</a></li>
          <li>연락처: <a href="tel:010-3343-4000" class="hover:text-blue-600">010-3343-4000</a></li>
          <li>이메일: <a href="mailto:duonedu@duonedu.net" class="hover:text-blue-600">duonedu@duonedu.net</a></li>
          <li>웹사이트: <a href="https://www.duonedu.info" target="_blank" rel="noopener noreferrer" class="hover:text-blue-600">www.duonedu.info</a></li>
        </ul>
      </div>

      <!-- Business Information -->
      <div>
        <h4 class="font-semibold text-gray-900 mb-3">사업자 정보</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li>사업자등록번호: 264-87-01676</li>
          <li>통신판매업신고번호: 2020-경기평택-0204</li>
          <li>주소: 경기도 평택시 고덕중앙로 322 704호</li>
        </ul>
        <div class="mt-4 pt-4 border-t border-gray-200">
          <h5 class="font-semibold text-gray-700 mb-2 text-sm">무통장 입금</h5>
          <p class="text-sm text-gray-600">1005-903-896511 우리은행</p>
          <p class="text-sm text-gray-600">예금주: 두온교육(주)</p>
        </div>
      </div>

      <!-- Social Media & Links -->
      <div>
        <h4 class="font-semibold text-gray-900 mb-3">소셜 미디어</h4>
        <ul class="space-y-2 text-sm">
          <li>
            <a href="https://www.youtube.com/@mintorain7" target="_blank" rel="noopener noreferrer" class="text-gray-600 hover:text-red-600 flex items-center gap-2">
              <span>📺</span> 유튜브
            </a>
          </li>
          <li>
            <a href="https://www.instagram.com/mintorain/" target="_blank" rel="noopener noreferrer" class="text-gray-600 hover:text-pink-600 flex items-center gap-2">
              <span>📷</span> 인스타그램
            </a>
          </li>
          <li>
            <a href="https://www.facebook.com/mintorain" target="_blank" rel="noopener noreferrer" class="text-gray-600 hover:text-blue-700 flex items-center gap-2">
              <span>👥</span> 페이스북
            </a>
          </li>
          <li>
            <a href="https://x.com/mintorain7" target="_blank" rel="noopener noreferrer" class="text-gray-600 hover:text-black flex items-center gap-2">
              <span>𝕏</span> X (Twitter)
            </a>
          </li>
          <li>
            <a href="https://open.kakao.com/o/gpLP613g" target="_blank" rel="noopener noreferrer" class="text-gray-600 hover:text-yellow-500 flex items-center gap-2">
              <span>💬</span> 카카오톡 오픈채팅
            </a>
          </li>
          <li>
            <a href="http://pf.kakao.com/_UzjZG/chat" target="_blank" rel="noopener noreferrer" class="text-gray-600 hover:text-yellow-500 flex items-center gap-2">
              <span>🔧</span> 고객센터
            </a>
          </li>
          <li>
            <a href="https://mintorain-webapp.pages.dev/" target="_blank" rel="noopener noreferrer" class="text-gray-600 hover:text-blue-600 flex items-center gap-2">
              <span>🏠</span> 홈페이지
            </a>
          </li>
        </ul>
      </div>
    </div>

    <!-- Copyright -->
    <div class="border-t border-gray-200 pt-6 text-center">
      <p class="text-sm text-gray-500">
        © <span id="year"></span> 두온교육(주) × 미래이음연구소. All rights reserved.
      </p>
    </div>
  </div>
</footer>

<script>
  document.getElementById('year').textContent = new Date().getFullYear();
</script>
```

### Vue Component

```vue
<template>
  <footer class="bg-gray-50 border-t border-gray-200 py-12 px-6">
    <div class="max-w-7xl mx-auto">
      <!-- Company Header -->
      <div class="mb-8">
        <h3 class="text-2xl font-bold text-gray-900 mb-4">
          두온교육(주) × 미래이음연구소
        </h3>
      </div>

      <!-- Main Content Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-8">
        <!-- Contact Information -->
        <div>
          <h4 class="font-semibold text-gray-900 mb-3">연락처</h4>
          <ul class="space-y-2 text-sm text-gray-600">
            <li>대표전화: <a href="tel:070-5089-5960" class="hover:text-blue-600">070-5089-5960</a></li>
            <li>연락처: <a href="tel:010-3343-4000" class="hover:text-blue-600">010-3343-4000</a></li>
            <li>이메일: <a href="mailto:duonedu@duonedu.net" class="hover:text-blue-600">duonedu@duonedu.net</a></li>
            <li>웹사이트: <a href="https://www.duonedu.info" target="_blank" rel="noopener noreferrer" class="hover:text-blue-600">www.duonedu.info</a></li>
          </ul>
        </div>

        <!-- Business Information -->
        <div>
          <h4 class="font-semibold text-gray-900 mb-3">사업자 정보</h4>
          <ul class="space-y-2 text-sm text-gray-600">
            <li>사업자등록번호: 264-87-01676</li>
            <li>통신판매업신고번호: 2020-경기평택-0204</li>
            <li>주소: 경기도 평택시 고덕중앙로 322 704호</li>
          </ul>
          <div class="mt-4 pt-4 border-t border-gray-200">
            <h5 class="font-semibold text-gray-700 mb-2 text-sm">무통장 입금</h5>
            <p class="text-sm text-gray-600">1005-903-896511 우리은행</p>
            <p class="text-sm text-gray-600">예금주: 두온교육(주)</p>
          </div>
        </div>

        <!-- Social Media & Links -->
        <div>
          <h4 class="font-semibold text-gray-900 mb-3">소셜 미디어</h4>
          <ul class="space-y-2 text-sm">
            <li v-for="link in socialLinks" :key="link.name">
              <a
                :href="link.url"
                target="_blank"
                rel="noopener noreferrer"
                :class="['text-gray-600 flex items-center gap-2', link.hoverClass]"
              >
                <span>{{ link.emoji }}</span> {{ link.name }}
              </a>
            </li>
          </ul>
        </div>
      </div>

      <!-- Copyright -->
      <div class="border-t border-gray-200 pt-6 text-center">
        <p class="text-sm text-gray-500">
          © {{ currentYear }} 두온교육(주) × 미래이음연구소. All rights reserved.
        </p>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { computed } from 'vue';

const currentYear = computed(() => new Date().getFullYear());

const socialLinks = [
  { name: '유튜브', url: 'https://www.youtube.com/@mintorain7', emoji: '📺', hoverClass: 'hover:text-red-600' },
  { name: '인스타그램', url: 'https://www.instagram.com/mintorain/', emoji: '📷', hoverClass: 'hover:text-pink-600' },
  { name: '페이스북', url: 'https://www.facebook.com/mintorain', emoji: '👥', hoverClass: 'hover:text-blue-700' },
  { name: 'X (Twitter)', url: 'https://x.com/mintorain7', emoji: '𝕏', hoverClass: 'hover:text-black' },
  { name: '카카오톡 오픈채팅', url: 'https://open.kakao.com/o/gpLP613g', emoji: '💬', hoverClass: 'hover:text-yellow-500' },
  { name: '고객센터', url: 'http://pf.kakao.com/_UzjZG/chat', emoji: '🔧', hoverClass: 'hover:text-yellow-500' },
  { name: '홈페이지', url: 'https://mintorain-webapp.pages.dev/', emoji: '🏠', hoverClass: 'hover:text-blue-600' },
];
</script>
```

## Customization Options

### Minimal Footer (Simple)

```jsx
export default function MinimalFooter() {
  return (
    <footer className="bg-gray-900 text-white py-8 px-6">
      <div className="max-w-7xl mx-auto text-center">
        <p className="text-sm mb-2">두온교육(주) × 미래이음연구소</p>
        <p className="text-xs text-gray-400 mb-2">
          대표전화: 070-5089-5960 | 이메일: duonedu@duonedu.net
        </p>
        <p className="text-xs text-gray-400">
          © {new Date().getFullYear()} All rights reserved.
        </p>
      </div>
    </footer>
  );
}
```

### Dark Theme Footer

```jsx
export default function DarkFooter() {
  return (
    <footer className="bg-gray-900 text-white py-12 px-6">
      <div className="max-w-7xl mx-auto">
        <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
          {/* Contact */}
          <div>
            <h4 className="font-bold text-lg mb-4 text-blue-400">연락처</h4>
            <ul className="space-y-2 text-sm text-gray-300">
              <li>대표전화: <a href="tel:070-5089-5960" className="hover:text-blue-400">070-5089-5960</a></li>
              <li>이메일: <a href="mailto:duonedu@duonedu.net" className="hover:text-blue-400">duonedu@duonedu.net</a></li>
            </ul>
          </div>

          {/* Business Info */}
          <div>
            <h4 className="font-bold text-lg mb-4 text-blue-400">사업자 정보</h4>
            <p className="text-sm text-gray-300">사업자등록번호: 264-87-01676</p>
            <p className="text-sm text-gray-300">경기도 평택시 고덕중앙로 322 704호</p>
          </div>

          {/* Social */}
          <div>
            <h4 className="font-bold text-lg mb-4 text-blue-400">소셜 미디어</h4>
            <div className="flex gap-4">
              <a href="https://www.youtube.com/@mintorain7" className="hover:text-red-500">📺</a>
              <a href="https://www.instagram.com/mintorain/" className="hover:text-pink-500">📷</a>
              <a href="https://www.facebook.com/mintorain" className="hover:text-blue-500">👥</a>
              <a href="https://x.com/mintorain7" className="hover:text-gray-400">𝕏</a>
            </div>
          </div>
        </div>

        <div className="border-t border-gray-700 mt-8 pt-6 text-center text-sm text-gray-400">
          © {new Date().getFullYear()} 두온교육(주) × 미래이음연구소. All rights reserved.
        </div>
      </div>
    </footer>
  );
}
```

---

## Mode 2: 맞춤 푸터 제작 (Custom Footer Templates)

### Custom Footer Template - React

사용자 정보를 기반으로 생성되는 맞춤형 템플릿입니다.

```jsx
// components/CustomFooter.jsx
import React from 'react';

export default function CustomFooter({
  companyName = "Your Company",
  email = "contact@company.com",
  phone = "02-1234-5678",
  address = "",
  businessNumber = "",
  socialLinks = [],
  website = "",
  bankAccount = null
}) {
  return (
    <footer className="bg-gray-50 border-t border-gray-200 py-12 px-6">
      <div className="max-w-7xl mx-auto">
        {/* Company Header */}
        <div className="mb-8">
          <h3 className="text-2xl font-bold text-gray-900 mb-4">
            {companyName}
          </h3>
        </div>

        {/* Main Content Grid */}
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-8">
          {/* Contact Information */}
          <div>
            <h4 className="font-semibold text-gray-900 mb-3">연락처</h4>
            <ul className="space-y-2 text-sm text-gray-600">
              {phone && (
                <li>전화: <a href={`tel:${phone}`} className="hover:text-blue-600">{phone}</a></li>
              )}
              {email && (
                <li>이메일: <a href={`mailto:${email}`} className="hover:text-blue-600">{email}</a></li>
              )}
              {website && (
                <li>웹사이트: <a href={website} target="_blank" rel="noopener noreferrer" className="hover:text-blue-600">{website}</a></li>
              )}
            </ul>
          </div>

          {/* Business Information */}
          {(address || businessNumber || bankAccount) && (
            <div>
              <h4 className="font-semibold text-gray-900 mb-3">사업자 정보</h4>
              <ul className="space-y-2 text-sm text-gray-600">
                {businessNumber && <li>사업자등록번호: {businessNumber}</li>}
                {address && <li>주소: {address}</li>}
              </ul>
              {bankAccount && (
                <div className="mt-4 pt-4 border-t border-gray-200">
                  <h5 className="font-semibold text-gray-700 mb-2 text-sm">입금 정보</h5>
                  <p className="text-sm text-gray-600">{bankAccount.account}</p>
                  <p className="text-sm text-gray-600">예금주: {bankAccount.holder}</p>
                </div>
              )}
            </div>
          )}

          {/* Social Media */}
          {socialLinks.length > 0 && (
            <div>
              <h4 className="font-semibold text-gray-900 mb-3">소셜 미디어</h4>
              <ul className="space-y-2 text-sm">
                {socialLinks.map((link, idx) => (
                  <li key={idx}>
                    <a
                      href={link.url}
                      target="_blank"
                      rel="noopener noreferrer"
                      className="text-gray-600 hover:text-blue-600 flex items-center gap-2"
                    >
                      {link.icon && <span>{link.icon}</span>}
                      {link.name}
                    </a>
                  </li>
                ))}
              </ul>
            </div>
          )}
        </div>

        {/* Copyright */}
        <div className="border-t border-gray-200 pt-6 text-center">
          <p className="text-sm text-gray-500">
            © {new Date().getFullYear()} {companyName}. All rights reserved.
          </p>
        </div>
      </div>
    </footer>
  );
}
```

### Custom Footer Usage Example

```jsx
// App.jsx
import CustomFooter from './components/CustomFooter';

export default function App() {
  return (
    <div>
      {/* Page content */}

      <CustomFooter
        companyName="ABC Corporation"
        email="contact@abc.com"
        phone="02-1234-5678"
        address="서울시 강남구 테헤란로 123"
        businessNumber="123-45-67890"
        website="https://abc.com"
        socialLinks={[
          { name: '인스타그램', url: 'https://instagram.com/abc', icon: '📷' },
          { name: '페이스북', url: 'https://facebook.com/abc', icon: '👥' }
        ]}
        bankAccount={{
          account: '123-456-789012 국민은행',
          holder: 'ABC Corporation'
        }}
      />
    </div>
  );
}
```

### Simplified Custom Footer (Minimal)

```jsx
export default function SimpleCustomFooter({
  companyName,
  email,
  phone
}) {
  return (
    <footer className="bg-gray-900 text-white py-8 px-6">
      <div className="max-w-7xl mx-auto text-center">
        <p className="text-sm mb-2">{companyName}</p>
        <p className="text-xs text-gray-400 mb-2">
          {phone && `전화: ${phone}`}
          {phone && email && ' | '}
          {email && `이메일: ${email}`}
        </p>
        <p className="text-xs text-gray-400">
          © {new Date().getFullYear()} All rights reserved.
        </p>
      </div>
    </footer>
  );
}
```

---

## When to Use This Skill

### Mode 1 (공통 푸터)
- 두온교육(주) × 미래이음연구소 관련 프로젝트
- 회사 공식 웹사이트, 랜딩 페이지
- 일관된 회사 정보가 필요한 경우

### Mode 2 (맞춤 푸터)
- 다른 회사/클라이언트 프로젝트
- 개인 포트폴리오, 블로그
- 커스터마이징이 필요한 경우
- 다양한 정보 구조가 필요한 경우

## Output Options

Specify format preference:
- **React Component** (default) - `format: react`
- **HTML + Tailwind** - `format: html`
- **Vue Component** - `format: vue`
- **Minimal Version** - `variant: minimal`
- **Dark Theme** - `variant: dark`
