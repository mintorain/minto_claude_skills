---
name: automation-workflow-builder
description: Next.js와 Node.js를 활용하여 커스텀 자동화 워크플로우를 설계하고 구현하는 스킬. API 연동과 스케줄링을 통해 복잡한 비즈니스 로직을 자동화합니다.
version: 1.1.0
author: BSD Vibe Coding Center
tags: [automation, nextjs, nodejs, trigger-dev, cron-jobs, webhooks]
---

# ⚡ Next.js 자동화 워크플로우 빌더 스킬

이 스킬은 BSD 바이브코딩 수강생들이 **Next.js와 Node.js**를 사용하여 **커스텀 자동화 시스템**을 구축하고 업무 효율을 극대화할 수 있도록 돕습니다.

## 📋 이 스킬이 하는 일

1. **자동화 설계**: 데이터 흐름 분석 및 최적의 자동화 로직 설계
2. **API 연동**: 외부 서비스(Notion, Slack, Discord 등)의 API를 Node.js로 제어
3. **스케줄링 구현**: Vercel Cron Jobs 또는 GitHub Actions를 이용한 정기 작업 설정
4. **웹훅(Webhook) 처리**: 외부 이벤트 실시간 수신 및 응답 시스템 구축
5. **모니터링**: 자동화 실행 로그 및 에러 알림 시스템 구현

## 🎯 언제 이 스킬을 사용하나요?

- "사용자가 폼을 제출하면 자동으로 PDF를 생성해서 이메일로 보내고 싶어요"
- "매일 아침 특정 사이트의 데이터를 크롤링해서 슬랙으로 보고받고 싶어요"
- "결제가 완료되면 자동으로 수강 권한을 부여하고 웰컴 메시지를 보내고 싶어요"

## 🛠️ 기술 스택 (Code-First Automation)

### 1. Framework

- **Next.js (App Router)**: API Endpoint 및 Webhook Handler 구축
- **Node.js**: 고성능 백엔드 로직 처리

### 2. Automation Tools

- **Trigger.dev**: 복잡한 워크플로우를 코드로 작성하고 가시화
- **Inngest**: 신뢰성 높은 이벤트 기반 자동화
- **Upstash (QStash)**: 서버리스 환경을 위한 메시지 큐 및 스케줄링

### 3. Core Libraries

- **Axios / Fetch**: 외부 API 통신
- **Zustand / Prisma**: 상태 관리 및 데이터 처리

## 💻 구현 예시 (Next.js API Routes)

### 1. Webhook Handler (app/api/webhook/route.ts)

```typescript
import { NextResponse } from "next/server";

export async function POST(req: Request) {
  try {
    const data = await req.json();

    // 1. 데이터 검증 및 처리
    console.log("Webhook received:", data);

    // 2. 외부 API 호출 (예: Slack 알림)
    await fetch(process.env.SLACK_WEBHOOK_URL!, {
      method: "POST",
      body: JSON.stringify({ text: `새로운 이벤트 발생: ${data.message}` }),
    });

    return NextResponse.json({ success: true });
  } catch (error) {
    return NextResponse.json({ success: false }, { status: 500 });
  }
}
```

### 2. Scheduled Task (Vercel Cron)

```typescript
// app/api/cron/daily-report/route.ts
export async function GET() {
  // 매일 아침 전날 데이터를 요약하여 이메일 발송
  const summary = await generateDailySummary();
  await sendEmail("admin@example.com", "일간 보고서", summary);

  return new Response("OK");
}
```

## 📊 자동화 시나리오

### 1. 리드 관리 시스템

- Tally 폼 제출 → Next.js API 수신 → Notion DB 저장 → Slack 즉시 알림

### 2. 콘텐츠 자동 배포

- Notion 글 작성 완료 → Trigger.dev 감지 → 이미지 최적화 → SNS API를 통해 자동 게시

## 💬 예제 대화

**사용자**: "구글 시트에 행이 추가되면 자동으로 슬랙 메시지를 보내는 시스템을 Next.js로 만들고 싶어"

**Claude**:
"Next.js API Routes와 Google Sheets API를 연동하여 자동화 시스템을 구축해드리겠습니다. Polling 방식이나 Webhook 방식을 선택할 수 있으며, Node.js 기반의 안정적인 연동 코드를 생성해 드릴게요..."

---

## 🎯 핵심 정리

이 스킬을 사용하면:
✅ **No-code 툴의 한계**를 뛰어넘는 복잡한 로직 구현 가능
✅ **비용 절감**: Zapier 등 유료 자동화 툴 비용을 획기적으로 줄임
✅ **확장성**: 우리 서비스의 DB와 직접 연동되는 강력한 시스템 구축
✅ **유지보수**: 모든 자동화 로직을 코드로 관리 (Git 버전 관리 가능)

**BSD 학생이라면**: 이제 단순한 웹사이트 제작을 넘어, 비즈니스의 운영 엔진을 직접 코딩할 수 있습니다! ⚡
