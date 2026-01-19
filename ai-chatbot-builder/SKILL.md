---
name: ai-chatbot-builder
description: Next.js와 Node.js를 기반으로 맞춤형 AI 챗봇을 구축하는 스킬. OpenAI, Anthropic API를 활용하여 지능형 비즈니스 챗봇을 개발합니다.
version: 1.1.0
author: BSD Vibe Coding Center
tags: [chatbot, ai, nextjs, nodejs, openai, langchain]
---

# 🤖 Next.js AI 챗봇 빌더 스킬

이 스킬은 BSD 바이브코딩 수강생들이 **Next.js와 Node.js**를 사용하여 **지능형 AI 챗봇**을 웹사이트에 직접 구축하고 배포할 수 있도록 돕습니다.

## 📋 이 스킬이 하는 일

1. **AI 엔진 설정**: OpenAI (GPT-4), Anthropic (Claude) 등 최적의 LLM 선택
2. **백엔드 구축**: Next.js API Routes (Route Handlers)를 사용한 챗봇 서버 구현
3. **프론트엔드 구현**: React(Next.js) 기반의 실시간 스트리밍 채팅 UI 제작
4. **지식베이스(RAG)**: 벡터 데이터베이스를 활용한 전용 데이터 학습 및 답변 최적화
5. **외부 연동**: Slack, Discord, 텔레그램 등 멀티 채널 연동 가이드

## 🎯 언제 이 스킬을 사용하나요?

- "Next.js 사이트에 우리 회사만의 AI 상담원을 넣고 싶어요"
- "PDF 문서를 학습해서 답변해주는 챗봇을 직접 개발하고 싶어요"
- "사용자 데이터를 분석해서 개인화된 추천을 해주는 AI 봇이 필요해요"

## 🛠️ 기술 스택 (Code-First)

### 1. Framework & Language

- **Next.js 14+ (App Router)**: 프론트엔드 및 API 서버 통합
- **TypeScript**: 안정적인 코드 개발

### 2. AI SDKs

- **AI SDK (Vercel)**: 텍스트 생성 및 스트리밍 최적화
- **LangChain / LlamaIndex**: 복잡한 체인 및 데이터 연동

### 3. Database & Vector Store

- **Supabase (pgvector)**: 사용자 관리 및 벡터 검색
- **Pinecone**: 대규모 데이터용 벡터 엔진

## 💻 Next.js 챗봇 구현 예시

### 1. Client UI (components/ChatBox.tsx)

```tsx
"use client";
import { useChat } from "ai/react";

export default function ChatBox() {
  const { messages, input, handleInputChange, handleSubmit } = useChat();

  return (
    <div className="flex flex-col w-full max-w-md mx-auto stretch">
      {messages.map((m) => (
        <div
          key={m.id}
          className={`whitespace-pre-wrap p-4 ${
            m.role === "user"
              ? "bg-slate-100"
              : "bg-blue-50 text-blue-900 border-l-4 border-blue-500"
          }`}
        >
          <strong>{m.role === "user" ? "👤 나: " : "🤖 AI: "}</strong>
          {m.content}
        </div>
      ))}
      <form onSubmit={handleSubmit}>
        <input
          className="fixed bottom-0 w-full max-w-md p-2 mb-8 border border-gray-300 rounded shadow-xl focus:outline-none focus:ring-2 focus:ring-blue-500"
          value={input}
          placeholder="무엇이든 물어보세요..."
          onChange={handleInputChange}
        />
      </form>
    </div>
  );
}
```

### 2. Server API (app/api/chat/route.ts)

```typescript
import { OpenAIStream, StreamingTextResponse } from "ai";
import OpenAI from "openai";

const openai = new OpenAI({ apiKey: process.env.OPENAI_API_KEY });

export async function POST(req: Request) {
  const { messages } = await req.json();
  const response = await openai.chat.completions.create({
    model: "gpt-4-turbo",
    stream: true,
    messages: [
      {
        role: "system",
        content: "당신은 BSD 바이브코딩 센터의 친절한 상담원입니다.",
      },
      ...messages,
    ],
  });

  const stream = OpenAIStream(response);
  return new StreamingTextResponse(stream);
}
```

## 📊 챗봇 유형별 활용 사례

### 1. 지식 기반 상담 봇 (RAG)

- 회사의 매뉴얼, 정책 PDF를 학습하여 답변
- API 연동으로 실시간 재고나 가격 정보 반영

### 2. 영업 및 리드 제네레이션 봇

- 대화를 통해 사용자의 니즈 파악 후 DB에 저장
- 관련 상품의 결제 링크(Check-out)로 유도

## 💬 예제 대화

**사용자**: "우리 쇼핑몰에 상품 추천해주는 AI 챗봇을 Next.js로 만들고 싶어"

**Claude**:
"Next.js와 OpenAI API를 사용하여 맞춤형 상품 추천 챗봇을 구축해드리겠습니다. 대화형 인터페이스를 통해 사용자의 취향을 분석하고, 내부 DB와 연동하여 최적의 상품을 제안하는 로직을 포함한 코드를 생성해 드릴게요..."

---

## 🎯 핵심 정리

이 스킬을 사용하면:
✅ **Vercel AI SDK**를 활용한 고성능 챗봇 구현
✅ **Stream 응답**으로 실제 사람과 대화하는 듯한 UX 제공
✅ **Node.js 백엔드**를 통해 보안 이슈(API Key 노출) 해결
✅ **Custom Data** 연동으로 우리 회사만의 특별한 AI 구축

**BSD 학생이라면**: 외부 유료 챗봇 솔루션에 의존하지 않고, 직접 AI 프로덕트를 개발하여 비즈니스 가치를 높일 수 있습니다! 🤖
