# SNU RTOS LAB Cloud Native 교육

이 프로젝트는 간단한 C HTTP 서버를 활용하여 Cloud Native 방법론의 기본 요소인 **Git**, **CI/CD**, **컨테이너화**, 그리고 **Kubernetes**를 학습하기 위한 교육 과정입니다. 

## 교육 목표
- Cloud Native 환경에서 소프트웨어 개발 및 배포 프로세스를 체험하고 이해하기
- Git 및 협업 전략, Jenkins를 이용한 CI/CD 파이프라인, Docker 컨테이너화, Kubernetes 오케스트레이션의 기초를 습득

---

## 교육 과정 개요

### 1~2주차: Git & Branch 전략

#### 개념
- **Version Control System (VCS)**: git 기본 커맨드와 원리
- **협업 전략**: branch, tag, GitHub flow, GitLab flow 등

#### 발표
  - **VCS**
    - git 기본 커맨드를 핸즈온으로 보여주기
    - git 커맨드의 원리를(add, commit, branch) 발표 자료로 설명
  - **협업 전략**
    - 커밋을 하고 merge하는 예시를 전략별로 보이기

#### 과제
- git이 익숙하지 않은 사람은 생활코딩을 보고 따라해보기, 익숙한 사람은 이외 git 커맨드  원리 탐구하기
- C HTTP 서버 코드를 활용하여 3명이 각자 기능을 구현하고 Pull Request를 통해 병합하는 협업 연습

---

### 3주차: Docker를 통한 컨테이너 이해

#### 개념
- **Docker**: docker command를 통해 컨테이너 기본 컨셉 이해
- **Container 원리**: container의 구성 요소 이해
  

#### 발표
- **전 세션**: 각자가 준비한 git 커맨드 및 자료 ...
- **Docker**
  - `docker run`, `docker exec` 등의 커맨드 핸즈온으로 보여주기
  - Dockerfile을 통한 docker image 설명
- **Container 원리**
  - docker를 포함한 container가 linux kernel 기능을 조합한 프로세스에 불과한다는 걸 이해

#### 과제
- C HTTP 서버를 Dockerfile로 컨테이너화하여 이미지 생성
- Linux container 직접 빌드 및 namespace 요소 이해

#### 참조
- https://zserge.com/posts/containers/

---

### 4~5주차: Kubernetes와 Orchestration

#### 개념
- **Kubernetes 기본 요소**: pod, service 등의 기본 요소
- **Kubernetes Cluster Architecture**: kube-scheduler, kubelet 등의 대표 요소

#### 발표
- **전 세션**: linux namespace에 대한 이해
- **Kubernetes 기본 요소**
  - pod, service, replicaset, deployment 등의 기본 요소 설명 및 yaml 설정 파일
  - kubectl을 통한 적용

#### 과제
- C HTTP 서버 컨테이너를 deployment로 운영
- kubernetes 요소 하나씩 선정하여 스터디

---

### 6주차: GitHub Actions를 통한 CI/CD 기본

#### 개념
- **CI/CD의 의의**: Continuous Integration과 Continuous Deployment의 차이와 의미
- **GitHub Actions의 역할**: 빌드 및 테스트 자동화 도구로서의 활용

#### 과제
- GitHub Actions 설치 및 Workflow 설정
- GitHub와 연동하여 C HTTP 서버의 빌드와 유닛 테스트 자동화
- 성공/실패 여부에 따른 알림(email, Slack)

---

### 7주차: Kubernetes(K3s)와 CICD 파이프라인 통합

#### 개념
- **Kubernetes 업데이트 전략**: Rolling Update, Blue-Green Deployment 등
- **CI/CD 파이프라인 전체 흐름**: 코드 변경 → Git push → Jenkins 빌드 → Docker 이미지 생성 → Kubernetes 업데이트

#### 과제
- Git push 시 Jenkins에서 빌드 → Docker Registry 등록 → Kubernetes 배포로 이어지는 파이프라인 완성

---

## 사용법

1. **C HTTP 서버 실행**
   - [서버 코드](./server.c)를 참고하여 서버를 빌드하고 실행합니다.
   - `gcc server.c -o server && ./server`를 통해 로컬에서 서버를 확인할 수 있습니다.

2. **과제 환경 준비**
   - Docker 및 Kubernetes 설치: [Docker 설치 가이드](https://docs.docker.com/get-docker/), [Minikube 설치 가이드](https://minikube.sigs.k8s.io/docs/start/)
   - Jenkins 설치: [Jenkins 설치 가이드](https://www.jenkins.io/doc/book/installing/)

3. **교육 진행**
   - 각 과제 내용을 참고하여 Git, CI/CD, Docker, Kubernetes 등을 체험합니다.
   - 각 과정의 과제과제를 수행하며 Cloud Native 개발 환경을 이해합니다.

---

## 프로젝트 구조
```
├── .github/workflows # github action 관련 설정 파일 
├── kubernetes/ # Kubernetes 관련 YAML 파일 
├── server.c # C HTTP 서버 코드 
├── Dockerfile # 컨테이너 이미지를 생성하기 위한 Dockerfile 
└── README.md # 프로젝트 안내 파일
```
