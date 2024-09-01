---
layout: single
title: "[JavaScript] 클래스(Class)와 모듈"
categories: JavaScript
tags: [JavaScript, Zerobase]
toc: true
author_profile: false
sidebar:
  nav: "docs"
---

자바스크립트의 클래스와 모듈의 특징을 간단하게 살펴보고, 클래스를 활용한 모듈화 방법도 간단하게 알아보도록 하자.

### 자바스크립트의 Class

- 객체를 만드는 5가지 방법 중 하나
- 여러 개의 객체를 만들 때 사용함
- 생성자 함수와 매우 유사하지만, 생성자 함수보다 좀 더 엄격하고, 생성자 함수에서 제공하지 않는 기능도 제공하기 때문에 문법적 설탕이라고 보기 어려움
- 새로운 객체 생성 메커니즘
- 클래스 내부는 코드 블록이 아니므로 클래스 내부에는 스코프가 없음
- 현실에서는 대부분 코드들이 분산되어 있어 코드를 한눈에 이해하기 어렵기 때문에 상속보다는 합성을 할 것을 추천!

### 자바스크립트의 모듈

- 애플리케이션과 분리되어 개별적으로 존재하다가 필요에 따라 다른 모듈에 의해 재사용됨
- 기능을 기준으로 파일 단위로 구분하며, 모듈은 자신만의 파일 스코프(모듈 스코프)를 가짐
- 따라서 자신만의 파일 스코프를 갖는 모듈의 모든 자산(모듈에 포함되어 있는 변수, 함수, 객체 등)은 캡슐화되어 다른 모듈에서 접근할 수 없음. 즉, 개별적 존재
- export된 자산에 한해 다른 모듈에서 재사용할 수 있음
- export의 종류로는 named export와 default export 가 있음
- 모듈에서 하나만 export 하는 것이 가장 좋기 때문에 기본적으로 default export를 사용함
- export 된 하나의 함수를 여러 모듈에서 import 해도 함수는 한 번만 생성됨
- 코드의 재사용성이 높아져서, 개발의 효율성과 유지 보수성이 향상됨

### 클래스를 활용한 모듈화 방법

그렇다면 클래스를 활용해서 모듈화를 어떻게 하는지 간단하게 살펴보자.

```javascript
// Car.js 파일 (모듈)
class Car {
  constructor(color, speed) {
    this.color = color;
    this.speed = speed;
  }

  accelerate(amount) {
    this.speed += amount;
  }

  break(amount) {
    this.speed -= amount;
  }

  getSpeed() {
    return this.speed;
  }
}

// Car 클래스를 외부에서 사용 가능하도록 export 함
export default Car;
```

```javascript
// main.js 파일
// Car.js 모듈이 export한 식별자를 import함
import Car from "./Car.js";

const myCar = new Car("red", 120);
myCar.accelerate(50);
console.log(myCar.getSpeed());
```
