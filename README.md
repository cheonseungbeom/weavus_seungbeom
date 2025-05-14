<div align="center"><a name="readme-top"></a>

# 쇼핑몰 프로젝트

**Spring Boot 기반 쇼핑몰 웹 애플리케이션**<br/>
사용자 계정 관리, 상품 관리, 장바구니 및 주문 기능을 포함한 풀스택 쇼핑몰 프로젝트입니다.

---

[**📖 문서**](#) · [**🔄 변경사항**](#) · [**📥 다운로드**](#) · [**⚡️ 기능 미리보기**](#)

</div>

---

<details>
<summary><kbd>Table of contents</kbd></summary>

- [📌 프로젝트 개요](#-프로젝트-개요)
- [✨ 주요 기능](#-주요-기능)
- [🛠 기술 스택](#-기술-스택)
- [🚀 시작하기](#-시작하기)
  - [로컬 개발 환경 설정](#로컬-개발-환경-설정)
  - [배포](#배포)
- [📦 프로젝트 구조](#-프로젝트-구조)
- [📋 변경사항](#-변경사항)
- [🤝 기여](#-기여)
- [📝 라이선스](#-라이선스)

</details>

---

## 📌 프로젝트 개요

Spring Boot를 기반으로 한 쇼핑몰 웹 애플리케이션으로, 사용자와 관리자 모두를 위한 직관적인 UI와 강력한 기능을 제공합니다. 

### 프로젝트 목표

- **사용자 친화적 인터페이스 제공**
- **안정적이고 확장 가능한 백엔드 아키텍처 구축**
- **효율적인 상품 및 주문 관리**

---

## ✨ 주요 기능

- **사용자 관리**
  - 회원가입, 로그인/로그아웃, 비밀번호 변경
- **상품 관리**
  - 상품 등록, 수정, 삭제
  - 상품 목록 및 상세 조회
- **장바구니**
  - 상품 추가 및 삭제
  - 총합 계산
- **주문 관리**
  - 주문 생성, 조회, 상태 업데이트
- **보안**
  - Spring Security 기반 인증/인가
  - CSRF 보호

---

## 🛠 기술 스택

- **Frontend**: Thymeleaf, HTML, CSS
- **Backend**: Spring Boot, Spring Security, JPA (Hibernate), QueryDSL
- **Database**: H2 (개발 환경), MySQL/PostgreSQL (배포 환경)
- **빌드 도구**: Maven
- **버전 관리**: Git

---

## 🚀 시작하기

### 로컬 개발 환경 설정

1. **필수 설치**
   - Java 17 이상
   - Maven
   - MySQL (또는 PostgreSQL)

2. **레포지토리 클론**
   ```bash
   git clone https://github.com/cheonseungbeom/weavus_seungbeom.git
   cd shop2

3. **의존성 설치**
  mvn clean install
4. **애플리케이션 설치**
  mvn spring-boot:run
5. **접속**
   http://localhost:81

## 📦 프로젝트 구조

src/
├── main/
│   ├── java/
│   │   └── com.example.shop/
│   │       ├── config/
│   │       ├── controller/
│   │       ├── domain/
│   │       ├── dto/
│   │       ├── repository/
│   │       └── service/
│   └── resources/
│       ├── static/
│       ├── templates/
│       └── application.properties
└── test/


## 🤝 기여
기여를 환영합니다! 버그 제보, 기능 요청 또는 PR을 통해 프로젝트 발전에 기여해주세요.

1. 레포지토리 포크

2. 변경사항 커밋

3. PR 생성
