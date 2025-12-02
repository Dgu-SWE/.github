<img width="1444" height="804" alt="image" src="https://github.com/user-attachments/assets/ebcd63f5-8a57-48b4-b9be-d00409963eac" />

# 🎓 나도 졸업할래


> **"매년 바뀌는 복잡한 졸업 요건, AI가 분석해 드립니다."**
>
> 2020~2025학년도 학제 개편 이력을 완벽하게 반영한 **동국대학교 지능형 학사 관리 챗봇 & 플랫폼**

## 🌟 Project Identity

**"기존의 졸업 계산기와 무엇이 다른가요?"**

나도 졸업할래는 단순한 학점 계산기가 아닙니다. 입학년도별로 상이한 학과 명칭 변경(공과대,AI융합,첨단융합), 전공 필수 과목 지정 변경, BSM 학점 변동 등 복잡하게 얽힌 학사 로직을 **데이터베이스화**하여 해결했습니다.

여기에 **DSPy 기반의 AI 에이전트**를 결합하여, 단순 조회를 넘어 개인화된 졸업 시뮬레이션과 자연어 상담을 제공합니다.

정보 과잉으로 인해 필요한 내용을 찾기 어려웠던 기존 시스템과 달리, 챗봇을 통해 빠르고 간편하게 조회하며 사용자가 원하는 정보만 선별적으로 얻을 수 있는 시스템입니다.

---
## 📦 UseCase Diagrma
<img width="14444" height="900" alt="image" src="https://github.com/user-attachments/assets/e70666e9-6b84-4280-97df-9494c9d22149" />
### 📋 주요 유즈케이스 명세

| 기능 (Use Case) | 설명 (Description) |
| :--- | :--- |
| **로그인** | 모든 서비스 이용의 전제 조건입니다. (모든 기능이 이를 Include 함) |
| **이수 내역 조회** | 사용자가 자신의 수강 기록(Transcript)을 조회하는 기능입니다. |
| **공지사항 확인** | 목록으로 공지사항을 확인하고 실제 공지 링크로 연결해주는 기능입니다. |
| **이전 대화 확인** | 과거에 챗봇과 나눴던 대화 히스토리를 불러오는 기능입니다. |
| **메시지 전송** | 챗봇 서비스의 핵심입니다. 사용자가 텍스트를 입력하는 행위입니다.<br>이 행위는 내부적으로 **졸업 요건 계산 / 공지 질문 / 수업 추천** 등으로 분기됩니다. |


---

## 💎 Key Features

### 1. 메인페이지
![Dashboard UI Image]
*(여기에 대시보드 UI 이미지를 넣어주세요)*

### 2. AI Chatbot
![Chatbot Interface Image]
*(여기에 챗봇 대화 화면 이미지를 넣어주세요)*

---

## 🏗️ System Architecture

<img width="1274" height="1002" alt="image" src="https://github.com/user-attachments/assets/82039c60-c8be-4123-95b1-26cde6c3a360" />

---

## 📚 Tech Stack

| Category | Technology |
| :--- | :--- |
| **Frontend** | React 19, React Router, CSS Modules |
| **Backend** | Spring Boot 3.4, Spring Data JPA, QueryDSL |
| **AI / ML** | Python FastAPI, **DSPy**, OpenAI GPT-4o |
| **Database** | PostgreSQL |
| **Infra** | CloudType |

---

## 🛠️ Technology Deep Dive

우리는 복잡한 현실 세계의 학사 행정을 시스템에 녹여내기 위해 다음과 같은 **기술적 설계**를 도입했습니다.

### 1. 다차원 졸업 요건 매칭 시스템 (DMBP Algorithm)
단순히 학번만으로 졸업 요건을 특정할 수 없는 문제를 해결하기 위해, **4가지 복합 키**를 사용하는 정규화된 DB 설계를 적용했습니다.
* **D**epartment (소속 단과대/학부: 공과대 → AI융합 → 첨단융합 변천사 반영)
* **M**ajor (전공: 컴퓨터공학전공 고정)
* **B**ase Year (입학년도: 학번 앞자리)
* **P**rogram Name (트랙: 심화/일반)

### 2. DSPy 기반 의도 추론 엔진 (AI Agent)
기존의 단순 프롬프트 엔지니어링을 넘어, **DSPy (Declarative Self-improving Python)** 프레임워크를 도입하여 AI의 답변 정확도를 극대화했습니다.
* **Router Agent:** 사용자 발화의 의도(단순 대화 vs 학사 질문)를 빠르게 분류
* **MCP Client:** 질문 해결에 필요한 데이터만 백엔드에서 선별적으로 조회하여 Hallucination 방지

### 3. 이수체계도 완벽 구현 (Data Integrity)
* **선수과목(Prerequisite) 로직:** `자료구조`를 들어야 `알고리즘`을 들을 수 있다는 과목 간의 의존성을 DB화하여 수강 가능 여부를 판별.
* **학수번호 매핑:** 구 학수번호(`CSE`)와 신 학수번호(`CSC`)를 통합 관리하여 학번과 무관하게 정확한 이수 여부 판단.

---

## 📂 Repositories

| Repository | Description |
| :--- | :--- |
| **[`gonnag-back`](./gonnag-back)** | **Core Server.** 인증, 졸업 계산 로직, MCP 데이터 제공자 |
| **[`gonnag-front`](./gonnag-front)** | **User Interface.** 반응형 웹 대시보드 및 채팅 인터페이스 |
| **[`gonnag-ai`](./gonnag-ai)** | **AI Engine.** 의도 분류 및 MCP 기반 답변 생성 |

---

### 👥 Team GonnaG
**동국대학교 소프트웨어공학과 졸업프로젝트**
| 이름 | 학과 | 역할 | 담당 파트 |
| :--: | :-- | :-- | :-- |
| **이재혁** | 컴퓨터공학전공 | **PM /AI** | 프로젝트 매니징, 챗봇 개발 |
| **황윤수** | 컴퓨터AI학부 | **Backend** | 백엔드 개발  |
| **조수현** | 컴퓨터공학전공 | **Backend** | 백엔드 개발 |
| **손승현** | 컴퓨터공학전공 | **Frontend** | 프론트엔드 개발 |

Copyright © 2025 GonnaG. All Rights Reserved.
