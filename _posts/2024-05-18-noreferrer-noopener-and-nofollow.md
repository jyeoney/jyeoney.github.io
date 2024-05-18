---
layout: single
title:  "[HTML] noreferrer, noopener, nofollow"
categories: HTML
tags: [HTML, Zerobase]
toc: true
author_profile: false
sidebar:
    nav: "docs"
---

HTML의 a 태그는 링크를 만드는 데 주로 사용되며, rel 속성으로 noreferrer, noopener, nofollow를 사용한다.

```HTML
<a href="링크할 페이지 주소" target="_blank" rel="noreferrer noopener nofollow">새 페이지의 링크</a>
```
target=”_blank” 속성을 사용하면 새 탭에서 페이지를 열 수 있음

## noreferrer
- 현재 요청을 보낸 페이지의 주소를 포함하는 referer 헤더를 생략하여, 링크에 연결된 외부 페이지로부터 사용자가 온 경로에 대한 정보를 마스킹 처리하여 알지 못하게 함

## noopener
- 새로운 탭에서 링크를 열 때, 새로 열린 사이트가 window.opener 객체를 조작하지 못하게 만듦
- window.opener 속성은 새롭게 연결된 페이지가 원본 페이지까지 참조하도록 하기 때문에 원본 페이지까지 성능이 저하될 수 있고, 원본 페이지에 직접적인 접근이 가능하도록 하면 피싱 공격을 받을 수 있음

구형 브라우저에서는 noreferre만 지원하는 경우도 있으므로 noopener, noreferrer 속성을 모두 사용하는 것 추천!

## nofollow
- 페이지 내 링크에 대한 검색엔진의 크롤링을 막아 링크된 페이지가 검색 엔진의 순위에 영향을 미치지 않음
- 검색엔진 최적화 (SEO)에 사용되지 않아야 할 링크에 사용하여 부적절한 방법으로 사이트의 검색 순위를 높이는 것, 무분별한 스팸 댓글이나 스팸 링크를 방지함