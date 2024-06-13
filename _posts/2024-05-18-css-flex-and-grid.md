---
layout: single
title:  "[CSS] Flex와 Grid"
categories: CSS
tags: [CSS, Zerobase]
toc: true
author_profile: false
sidebar:
    nav: "docs"
---

## Flex
### Flex란?
- 1차원의 레이아웃 시스템을 만들 수 있는 속성

### Flex에 부여할 수 있는 속성
1. Flex Container

    | 속성 | 의미 |
    |:---:|:---:|
    | display	| 플렉스 컨테이너를 정의 |
    | flex-flow	| flex-direction와 flex-wrap의 단축 속성 |
    | flex-direction | 플렉스 아이템의 주 축을 설정 |
    | flex-wrap	| 플렉스 아이템의 여러 줄 묶음(줄 바꿈) 설정 |
    | justify-content	| 주 축의 정렬 방법을 설정 |
    | align-content	| 교차 축의 정렬 방법을 설정(2줄 이상) |
    | align-items	| 교차 축에서 플렉스 아이템들의 정렬 방법을 설정(1줄) |
    | gap	| 각 아이템 사이의 간격을 설정 |

2. Flex Items

    | 속성 | 의미 |
    |:---:|:---:|
    | order | 플렉스 아이템의 순서를 설정 |
    | flex | flex-grow, flex-shrink, flex-basis의 단축 속성 |
    | flex-grow | 플렉스 아이템의 증가 너비 비율을 설정 |
    | flex-shrink | 플렉스 아이템의 감소 너비 비율을 설정 |
    | flex-basis | 플렉스 아이템의 (공간 배분 전) 기본 너비 설정 |
    | align-self | 교차 축에서 아이템의 정렬 방법을 설정 |

## Grid
### Grid란?
- 2차원(행과 열)의 레이아웃 시스템을 만들 수 있는 속성

### Grid에 부여할 수 있는 속성
1. Grid Container

    | 속성 | 의미 |
    |:---:|:---:|
    | display | 그리드 컨테이너를 정의 |
    | grid-template-rows | 각 행의 크기를 정의 |
    | grid-template-columns | 각 열의 크기를 정의 |
    | grid-template-areas | 그리드 영역의 이름을 참조하여 그리드 템플릿 설정 |
    | grid-template | grid-template-xxx의 단축 속성 |
    | row-gap | 행과 행 사이의 간격을 정의 |
    | column-gap | 열과 열 사이의 간격을 정의 |
    | gap | xxx-gap의 단축 속성 |
    | grid-auto-rows | 자동으로 행의 크기를 정의 |
    | grid-auto-columns | 자동으로 열의 크기를 정의 |
    | grid-auto-flow | 자동 배치 방식을 정의 |
    | grid | grid-template-xxx과 grid-auto-xxx의 단축 속성 |
    | align-content | 그리드 콘텐츠를 수직(열 축) 정렬 |
    | justify-content | 그리드 콘텐츠를 수평(행 축) 정렬 |
    | place-content | 	align-content와 justify-content의 단축 속성 |
    | align-items | 그리드 아이템들을 수직(열 축) 정렬 |
    | justify-items | 그리드 아이템들을 수평(행 축) 정렬 |
    | place-items	 | align-items와 justify-items의 단축 속성 |

2. Grid Items

    | 속성 | 의미 |
    |:---:|:---:|
    | grid-row-start | 그리드 아이템의 행 시작 위치 지정 |
    | grid-row-end | 그리드 아이템의 행 끝 위치 지정 |
    | grid-row | grid-row-xxx의 단축 속성(행 시작/끝 위치) |
    | grid-column-start | 그리드 아이템의 열 시작 위치 지정 |
    | grid-column-end | 그리드 아이템의 열 끝 위치 지정 |
    | grid-column | grid-column-xxx의 단축 속성(열 시작/끝 위치) |
    | grid-area | 영역 이름 설정 & grid-row와 grid-column의 단축 속성 |
    | align-self | 단일 그리드 아이템을 수직(열 축) 정렬 |
    | justify-self | 단일 그리드 아이템을 수평(행 축) 정렬 |
    | place-self | align-self와 justify-self의 단축 속성 |
    | order | 그리드 아이템의 배치 순서를 지정 |
    | z-index | 그리드 아이템의 쌓이는 순서를 지정 |

## Flex 와 Grid
1. Flex
- flex 는 1차원. 수평, 수직 영역 중 하나의 방향으로만 레이아웃을 나눌 수 있음
- 콘텐츠를 정렬할 때 사용 추천!

2. Grid
- grid 는 2차원. 수평, 수직 영역을 동시에 나눌 수 있음
- 전체 레이아웃을 정렬할 때 사용 추천!


*참고사이트: [CSS Flex 완벽 가이드](https://www.heropy.dev/p/Ha29GI),  [CSS Grid 완벽 가이드](https://www.heropy.dev/p/c6ROLZ)