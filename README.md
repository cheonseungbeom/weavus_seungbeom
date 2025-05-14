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
6. 
<details>
<summary><kbd>데이터 베이스 DLL</kbd></summary>
  -- shop.cart_item_seq definition

CREATE TABLE `cart_item_seq` (
  `next_val` bigint DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.cart_seq definition

CREATE TABLE `cart_seq` (
  `next_val` bigint DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.item definition

CREATE TABLE `item` (
  `item_id` bigint NOT NULL AUTO_INCREMENT,
  `item_detail` tinytext NOT NULL,
  `item_nm` varchar(50) NOT NULL,
  `item_sell_status` varchar(255) DEFAULT NULL,
  `price` int NOT NULL,
  `reg_time` datetime(6) DEFAULT NULL,
  `number` int DEFAULT '0',
  `update_time` datetime(6) DEFAULT NULL,
  `created_by` varchar(255) DEFAULT NULL,
  `modified_by` varchar(255) DEFAULT NULL,
  `stock_number` int NOT NULL,
  PRIMARY KEY (`item_id`)
) ENGINE=InnoDB AUTO_INCREMENT=254 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.item_img_seq definition

CREATE TABLE `item_img_seq` (
  `next_val` bigint DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.item_seq definition

CREATE TABLE `item_seq` (
  `next_val` bigint DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.`member` definition

CREATE TABLE `member` (
  `member_id` bigint NOT NULL AUTO_INCREMENT,
  `address` varchar(255) DEFAULT NULL,
  `email` varchar(255) DEFAULT NULL,
  `name` varchar(255) DEFAULT NULL,
  `password` varchar(255) DEFAULT NULL,
  `role` varchar(255) DEFAULT NULL,
  `reg_time` datetime(6) DEFAULT NULL,
  `update_time` datetime(6) DEFAULT NULL,
  `created_by` varchar(255) DEFAULT NULL,
  `modified_by` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`member_id`),
  UNIQUE KEY `UK_mbmcqelty0fbrvxp1q58dn57t` (`email`)
) ENGINE=InnoDB AUTO_INCREMENT=7 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.member_seq definition

CREATE TABLE `member_seq` (
  `next_val` bigint DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.order_item_seq definition

CREATE TABLE `order_item_seq` (
  `next_val` bigint DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.orders_seq definition

CREATE TABLE `orders_seq` (
  `next_val` bigint DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.test definition

CREATE TABLE `test` (
  `id` bigint NOT NULL AUTO_INCREMENT,
  `my_age` int NOT NULL,
  `my_info` varchar(255) DEFAULT NULL,
  `name` varchar(20) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.cart definition

CREATE TABLE `cart` (
  `cart_id` bigint NOT NULL,
  `reg_time` datetime(6) DEFAULT NULL,
  `update_time` datetime(6) DEFAULT NULL,
  `created_by` varchar(255) DEFAULT NULL,
  `modified_by` varchar(255) DEFAULT NULL,
  `member_id` bigint DEFAULT NULL,
  PRIMARY KEY (`cart_id`),
  UNIQUE KEY `UK7dds3r67nkhxm9sbs9r5obd46` (`member_id`),
  CONSTRAINT `FKix170nytunweovf2v9137mx2o` FOREIGN KEY (`member_id`) REFERENCES `member` (`member_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.cart_item definition

CREATE TABLE `cart_item` (
  `cart_item_id` bigint NOT NULL,
  `reg_time` datetime(6) DEFAULT NULL,
  `update_time` datetime(6) DEFAULT NULL,
  `created_by` varchar(255) DEFAULT NULL,
  `modified_by` varchar(255) DEFAULT NULL,
  `count` int NOT NULL,
  `cart_id` bigint DEFAULT NULL,
  `item_id` bigint DEFAULT NULL,
  PRIMARY KEY (`cart_item_id`),
  KEY `FK1uobyhgl1wvgt1jpccia8xxs3` (`cart_id`),
  KEY `FKdljf497fwm1f8eb1h8t6n50u9` (`item_id`),
  CONSTRAINT `FK1uobyhgl1wvgt1jpccia8xxs3` FOREIGN KEY (`cart_id`) REFERENCES `cart` (`cart_id`),
  CONSTRAINT `FKdljf497fwm1f8eb1h8t6n50u9` FOREIGN KEY (`item_id`) REFERENCES `item` (`item_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.item_img definition

CREATE TABLE `item_img` (
  `item_img_id` bigint NOT NULL,
  `reg_time` datetime(6) DEFAULT NULL,
  `update_time` datetime(6) DEFAULT NULL,
  `created_by` varchar(255) DEFAULT NULL,
  `modified_by` varchar(255) DEFAULT NULL,
  `img_name` varchar(255) DEFAULT NULL,
  `img_url` varchar(255) DEFAULT NULL,
  `ori_img_name` varchar(255) DEFAULT NULL,
  `repimg_yn` varchar(255) DEFAULT NULL,
  `item_id` bigint DEFAULT NULL,
  PRIMARY KEY (`item_img_id`),
  KEY `FKdd5u08y3ap4c46ayrqjf8g88m` (`item_id`),
  CONSTRAINT `FKdd5u08y3ap4c46ayrqjf8g88m` FOREIGN KEY (`item_id`) REFERENCES `item` (`item_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.orders definition

CREATE TABLE `orders` (
  `order_id` bigint NOT NULL,
  `reg_time` datetime(6) DEFAULT NULL,
  `update_time` datetime(6) DEFAULT NULL,
  `created_by` varchar(255) DEFAULT NULL,
  `modified_by` varchar(255) DEFAULT NULL,
  `order_date` datetime(6) DEFAULT NULL,
  `order_status` enum('CANCEL','ORDER') DEFAULT NULL,
  `member_id` bigint DEFAULT NULL,
  PRIMARY KEY (`order_id`),
  KEY `FKpktxwhj3x9m4gth5ff6bkqgeb` (`member_id`),
  CONSTRAINT `FKpktxwhj3x9m4gth5ff6bkqgeb` FOREIGN KEY (`member_id`) REFERENCES `member` (`member_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


-- shop.order_item definition

CREATE TABLE `order_item` (
  `order_item_id` bigint NOT NULL,
  `reg_time` datetime(6) DEFAULT NULL,
  `update_time` datetime(6) DEFAULT NULL,
  `created_by` varchar(255) DEFAULT NULL,
  `modified_by` varchar(255) DEFAULT NULL,
  `count` int NOT NULL,
  `order_price` int NOT NULL,
  `item_id` bigint DEFAULT NULL,
  `order_id` bigint DEFAULT NULL,
  PRIMARY KEY (`order_item_id`),
  KEY `FKija6hjjiit8dprnmvtvgdp6ru` (`item_id`),
  KEY `FKt4dc2r9nbvbujrljv3e23iibt` (`order_id`),
  CONSTRAINT `FKija6hjjiit8dprnmvtvgdp6ru` FOREIGN KEY (`item_id`) REFERENCES `item` (`item_id`),
  CONSTRAINT `FKt4dc2r9nbvbujrljv3e23iibt` FOREIGN KEY (`order_id`) REFERENCES `orders` (`order_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
</details>
## 📦 프로젝트 구조
```
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
```

## 🤝 기여
기여를 환영합니다! 버그 제보, 기능 요청 또는 PR을 통해 프로젝트 발전에 기여해주세요.

1. 레포지토리 포크

2. 변경사항 커밋

3. PR 생성
