---
layout: single
title:  "Git/Github 어휘 정리"
categories: Github
tags: [Zerobase, Github, Git]
toc: true
author_profile: false
sidebar:
    nav: "docs"
---

# Git/Github 어휘 정리

* Git: 분산 버전관리시스템. 프로젝트를 여러 컴퓨터로 협업하여 개발하면서 버전을 관리할 수 있음
* Github: Git을 기반으로 소스코드를 온라인에 저장 및 공유할 수 있도록 하는 소스코드 관리 서비스
* Working Directory: 작업하는 파일이 있는 Directory
* Repository: 소프트웨어 파일이나 폴더 등을 저장해두는 저장소
    * Local Repository: Local Git 프로젝트의 메타데이터와 데이터 정보가 저장되는 영역(저장소)
    * Remote Repository: Github 등의 서비스를 통한 온라인 저장소

* Staging Area: Git에 커밋할 파일이 올라가는 영역
* Branch: 사용자가 독립적으로 작업 진행 가능하도록 돕는 작업 흐름(가지). 각각의 브랜치는 독립적이므로 여러 작업을 동시에 진행 가능함
* Commit: Git에서 코드 수정사항을 기록하는 명령. Staging Area에 등록된 파일을 Local 저장소로 등록하는 것
* origin: Remote 저장소에 있는 코드
* head: 작업하고 있는 local 브랜치
* add:  Working Directory에서 Staging Area로 등록하는 것
* Push: Local Repository에서 변경된 파일을 Remote Repository로 등록하는 것
* Pull: Remote Repository 파일들을 Working Directory로 가져오는 것
* Fetch: Remote 저장소의 변경된 파일을 Local Repository로 전달하는 것
* Merge: Local 저장소의 변경사항을 Working Directory로 전달하는 것
* Checkout: 사용할 다른 브랜치를 지정
* test: origin
