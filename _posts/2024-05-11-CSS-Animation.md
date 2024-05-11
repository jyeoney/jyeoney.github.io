---
layout: single
title:  "[CSS] 애니메이션 최적화"
categories: [CSS]
tags: [CSS, Animation, Zerobase]
toc: true
author_profile: false
sidebar:
    nav: "docs"
---

## 브라우저 렌더링 과정
1. 파싱(Parsing): DOM Tree, CSSOM Tree 구성
2. 스타일(Style): DOM Tree, CSSOM Tree 를 기반으로 Render Tree를 생성
3. 레이아웃(Layout): Render Tree의 각 노드들의 위치, 크기, 너비 등 배치 계산
4. 그리기(Paint): Render Tree를 순회하며 레이어를 만들고 의 각 노드들을 실제 픽셀로 변환하여 그림
5. 합성(Composite): 그려진 레이어들을 순서에 맞게 합성하여 실제로 보는 화면을 만듦

### reflow & repaint
- reflow: 레이아웃 과정부터 다시 렌더링을 수행함
    - reflow 발생하는 속성: width, height, display 등
- repaint: 페인트 과정부터 다시 렌더링을 수행함
    - repaint 발생하는 속성: background-image, background-position, background-repeat 등

## CSS 애니메이션 최적화 방법
1. reflow, repaint 과정 최소화하기
- '메인스레드 점유 여부'가 성능을 결정하는 중요한 요소 중 하나임
- reflow, repaint 과정은 모두 메인 스레드를 점유하며, 이 과정이 자주 반복되면 페이지의 성능을 저하시킬 수 있음
- transform, opacity, cursor, orphans, perspective 등의 속성은 메인 스레드를 점유하지 않고 합성(Composite) 단계에서 렌더링을 할 수 있어 성능을 저하시키는 것을 막을 수 있음

2. will-change css 속성 사용하기
- 브라우저에게 변경될 속성을 미리 알려주어 브라우저가 적절한 준비를 할 수 있게 도와줌
- 과도하게 사용하면 오히려 페이지 속도를 늦추거나 성능에 문제를 일으킬 수 있음
- [will-change - CSS - MDN Web Docs](https://developer.mozilla.org/ko/docs/Web/CSS/will-change)


3. 3D Transform 사용하기
- 부모 요소의 영향을 받지 않으면서 독자적으로 애니메이션 구현이 가능함
- 메인쓰레드를 점유하지 않아 성능을 저하시키지 않음
- 3차원 공간을 표현 가능해 보다 복잡하고 사실적인 애니메이션 구현이 가능함

