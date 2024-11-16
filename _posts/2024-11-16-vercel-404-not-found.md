---
layout: single
title: "Vercel 배포 후 404 Not Found가 떴다!"
categories: FRONTEND
tags: [FRONTEND]
toc: true
author_profile: false
sidebar:
  nav: "docs"
---

Vite + React + TypeScript로 구현한 개인프로젝트를 Vercel을 통해서 배포했다.
<br>

### 문제 상황

로컬환경에서는 페이지 이동이 에러 없이 잘 되었는데, 배포한 사이트에서는 새로고침을 하거나, 주소창을 통해 들어갔을 때 404 오류가 발생했다. 이러한 404 오류는 클라이언트가 서버에 요청한 리소스를 찾을 수 없을 때 주로 발생한다.
<br>

### 원인

React 앱은 클라이언트 사이드 라우팅을 사용한다. 즉, 페이지 이동이 브라우저 내에서 처리되므로, 브라우저에서 URL을 해석한다.
<br>
그와 달리 Vercel은 요청된 URL을 서버 측에서 처리하며, 요청된 URL에 맞는 정적 파일이나 API를 찾게 된다. 그런데, 찾을 수 없으므로 404 오류가 발생하게 되는 것이다.
<br>
따라서 vercel.json 파일에 routes 또는 rewrites 설정을 추가하여, 서버가 클라이언트 사이드 라우팅을 지원하도록 만들어주어야 한다!!

### 해결방법

1. 프로젝트 루트 디렉터리에 vercel.json 파일 추가
2. vercel.json에는 아래의 2가지 코드 중 하나 작성

   ```json
   {
     "routes": [
       {
         "src": "/[^.]+",
         "dest": "/",
         "status": 200
       }
     ]
   }
   ```

   ```json
   {
     "rewrites": [
       {
         "source": "/(.*)",
         "destination": "/index.html"
       }
     ]
   }
   ```

- 이 코드들은 Vercel에게 모든 경로를 React의 진입점(index.html)으로 보내도록 알려주는 역할을 한다!

3. Vercel에 다시 배포
