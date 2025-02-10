---
layout: single
title: "Next.js params 타입 에러 해결기.md"
categories: FRONTEND
tags: [FRONTEND, Next.js, TypeScript]
toc: true
author_profile: false
sidebar:
  nav: "docs"
---

### 🔥 문제 상황

Next.js 프로젝트에서 npm run build 실행 시 다음과 같은 타입 오류가 발생했다.

```typescript
Type error: Type 'pageProps' does not satisfy the constraint 'PageProps'. Types of property 'params' are incompatible
```

![Image](https://github.com/user-attachments/assets/6fe0118b-77ef-42e1-95b0-7a8772adb174)

### 🔎 원인 분석

기존 코드는 아래와 같다.

```typescript
import ChatRoom from '@/app/chat/components/ChatRoom';

type ChatPageProps = {
  params: { chatRoomId: string };
};

const ChatPage = async ({ params }: ChatPageProps) => {
  const { chatRoomId } = await params; // ⚠️typeError 발생

  return (
    <div className="p-4 space-y-4">
      <div className="mt-4">
        <ChatRoom chatRoomId={chatRoomId} />
      </div>
    </div>
  );
};
export default ChatPage;
```

Next.js 최신 버전에서는 params가 비동기적으로 처리된다.
즉, params 가 기존 동기 방식이 아니라 Promise 객체로 반환되기 때문에,기존 코드에서는 TypeScript가 이를 올바르게 인식하지 못해 타입 오류가 발생했다.

### 🔑 해결 방법

1.  TypeScript가 params를 올바르게 인식하도록 PageProps 타입에서 params를 `Promise`로 감싸기
    - Next.js에서 params가 비동기적으로 제공될 경우, TypeScript가 이를 정확히 이해하려면 params의 타입을 Promise<>로 감싸야 한다!
2.  그 후 비동기 함수 내에서 `await`을 사용해 params 값에 접근하기
    - await을 사용하면 Promise가 **완전히 해결될 때까지** 기다렸다가 실제 값을 가져올 수 있다!

<br>
이렇게 타입을 비동기 방식으로 맞춰줌으로써 TypeScript가 올바르게 추론할 수 있게 되므로 정상적으로 실행될 것이다!

```typescript
import ChatRoom from '@/app/chat/components/ChatRoom';

type ChatPageProps = {
  params: Promise<{
    chatRoomId: string;
  }>;
};

const ChatPage = async ({ params }: ChatPageProps) => {
  const { chatRoomId } = await params;

  return (
    <div className="p-4 space-y-4">
      <div className="mt-4">
        <ChatRoom chatRoomId={chatRoomId} />
      </div>
    </div>
  );
};

export default ChatPage;
```
