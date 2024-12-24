# SNU RTOS LAB Cloud Native 교육

이 프로젝트는 간단한 C HTTP 서버를 활용하여 Cloud Native 방법론의 기본 요소인 **Git**, **CI/CD**, **컨테이너화**, 그리고 **Kubernetes**를 학습하기 위한 교육 과정입니다. 

## 교육 목표
- Cloud Native 환경에서 소프트웨어 개발 및 배포 프로세스를 체험하고 이해하기
- Git 및 협업 전략, Jenkins를 이용한 CI/CD 파이프라인, Docker 컨테이너화, Kubernetes 오케스트레이션의 기초를 습득

---

## 교육 과정 개요

### 1주차: Git & Branch 전략

#### 개념
- **Version Control System (VCS)**: git의 기본 사용법 (stage, commit, push 등)
- **협업 전략**: branch, tag, GitHub flow, GitLab flow 등

#### 실습 과제
현재 있는 server.c 코드 활용하여
1. "/" 경로에서만 응답이 나오게 만들기
2. 경로에 없는 페이지에서는 404 Not Found page 만들기
3. "/rtos" 페이지에서 다른 안내 문구 출력하기

이를 3명이 브랜치를 활용하여 나눈 이후에 합친 이후 step1 브랜치에 push하기

---

## 사용법

1. **C HTTP 서버 실행**
  - [서버 코드](./server.c)를 참고하여 서버를 빌드하고 실행합니다.
  - `gcc server.c -o server && ./server`를 통해 로컬에서 서버를 확인할 수 있습니다.

---

## 프로젝트 구조
```
├── .github/workflows # github action 관련 설정 파일 
├── kubernetes/ # Kubernetes 관련 YAML 파일 
├── server.c # C HTTP 서버 코드 
├── Dockerfile # 컨테이너 이미지를 생성하기 위한 Dockerfile 
└── README.md # 프로젝트 안내 파일
```