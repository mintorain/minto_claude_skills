---
name: payment-integration
description: Toss Payments, Stripe 등 최신 결제 시스템을 Next.js에 통합하는 스킬. 정기결제, 보안 결제, 웹훅 처리를 전문적으로 다룹니다.
version: 1.1.0
author: BSD Vibe Coding Center
tags: [payment, toss, stripe, nextjs, nodejs, checkout]
---

# 💳 Next.js 결제 시스템 통합 스킬

이 스킬은 BSD 바이브코딩 수강생들이 **Next.js와 Node.js**를 사용하여 **안전하고 전문적인 결제 시스템**을 구축할 수 있도록 돕습니다.

## 📋 이 스킬이 하는 일

1. **플랫폼 전략**: 비즈니스 모델(일회성/구독)에 맞는 최적의 PG사(Toss, Stripe) 선정
2. **Next.js 통합**: 클라이언트 사이드 결제 요청 및 서버 사이드 승인 로직 구현
3. **웹훅(Webhook) 연동**: 결제 완료, 취소 등 이벤트를 비동기로 처리하여 DB 동기화
4. **보안 및 검증**: 데이터 위변조 방지 및 서버 사이드 금액 검증 로직 구현
5. **구독 관리**: Stripe Billing 등을 활용한 자동 결제 및 멤버십 연동

## 🎯 언제 이 스킬을 사용하나요?

- "Next.js 쇼핑몰에 토스페이먼츠 유젯(Payment Widget)을 넣고 싶어요"
- "Stripe를 사용해 글로벌 구독 서비스를 만들고 싶어요"
- "결제가 완료되면 자동으로 알림톡을 보내고 수강 권한을 열어주고 싶어요"

## 🛠️ 추천 기술 스택

### 1. Payment Gateways

- **Toss Payments**: 국내 결제 최강자, 위젯 기반의 간편한 연동
- **Stripe**: 글로벌 및 구독 결제 표준

### 2. Implementation

- **Next.js App Router**: API Route Handlers를 활용한 결제 승인
- **Server Actions**: 보안이 강화된 데이터 처리

## 💻 구현 예시 (Next.js + Toss Payments)

### 1. Server Side (app/api/payment/confirm/route.ts)

```typescript
import { NextResponse } from "next/server";

export async function POST(req: Request) {
  const { paymentKey, orderId, amount } = await req.json();

  // 1. 서버 사이드 금액 검증 로직 추가 필수
  // const product = await db.product.findUnique({ where: { orderId } });
  // if (product.price !== amount) throw new Error('Invalid amount');

  const secretKey = process.env.TOSS_SECRET_KEY;
  const basicToken = Buffer.from(`${secretKey}:`).toString("base64");

  const response = await fetch(
    "https://api.tosspayments.com/v1/payments/confirm",
    {
      method: "POST",
      headers: {
        Authorization: `Basic ${basicToken}`,
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ paymentKey, orderId, amount }),
    }
  );

  const result = await response.json();
  if (response.ok) {
    // DB 업데이트 등 후처리 수행
    return NextResponse.json(result);
  } else {
    return NextResponse.json(result, { status: response.status });
  }
}
```

### 2. Client Side (components/Checkout.tsx)

```tsx
"use client";
import { loadTossPayments } from "@tosspayments/payment-sdk";

export default function Checkout() {
  const handlePayment = async () => {
    const tossPayments = await loadTossPayments(
      process.env.NEXT_PUBLIC_TOSS_CLIENT_KEY!
    );

    await tossPayments.requestPayment("카드", {
      amount: 50000,
      orderId: "ORDER_123",
      orderName: "Next.js 마스터클래스",
      successUrl: `${window.location.origin}/success`,
      failUrl: `${window.location.origin}/fail`,
    });
  };

  return <button onClick={handlePayment}>50,000원 결제하기</button>;
}
```

## ⚠️ 보안 체크리스트

- **금액 검증**: 반드시 서버 사이드에서 실제 DB의 가격과 비교 검증
- **API Key 관리**: Secret Key는 절대 클라이언트에 노출하지 말고 `.env`로 관리
- **멱등성(Idempotency)**: 중복 결제 방지를 위한 `Idempotency-Key` 활용

## 💬 예제 대화

**사용자**: "토스페이먼츠로 정기 결제 기능을 Next.js에 넣고 싶어"

**Claude**:
"Next.js App Router와 토스페이먼츠 빌링 API를 사용하여 안전한 정기 결제 시스템을 구축해드리겠습니다. 카드 등록부터 예약 결제 로직, 그리고 결제 결과 웹훅 처리까지 포함된 코드를 생성해 드릴게요..."

---

## 🎯 핵심 정리

이 스킬을 사용하면:
✅ **안전한 결제 아키텍처**: 서버 사이드 검증이 포함된 견고한 시스템
✅ **최신 연동 방식**: Toss UI Widget, Stripe Checkout 등 최신 트렌드 반영
✅ **비즈니스 확장성**: 정기 구독, 부분 취소, 에스크로 등 복잡한 기능 지원
✅ **안정적인 운영**: 웹훅 처리를 통한 데이터 불일치 문제 해결

**BSD 학생이라면**: 이제 단순한 웹사이트를 넘어, 실제 수익이 발생하는 비즈니스 플랫폼을 직접 개발할 수 있습니다! 💳
