![git-image-001](https://github.com/beyond-sw-camp/be08-1st-2go-lofi/assets/82626246/f82e1b48-88e4-40af-882e-afc5e1465fd7)

<br><br>
# 🔎 잃어버린 물건을 찾아서
기간 : 2024.05.25 ~ 2024.06.03

<br>

## 📖 프로젝트 개요
도시화가 진행됨에 따라 거주 인구가 증가하고, 대중교통 이용객 및 관광객의 증가로 유동 인구 또한 증가하고 있다. <br>
이로 인해 분실물 발생 가능성이 커짐에 따라 관리의 복잡성, 효율적 관리의 필요성이 발생하고 있다. <br>

이러한 경우에 사용자가 습득물을 등록하고, 분실물을 쉽게 찾을 수 있는 시스템이다. <br>
행정복지센터 무인 택배 보관함을 중계로 사용하여 대면 방식의 물품 찾아주기의 위험성을 낮추고 이 시스템을 통해 분실물의 회수율을 높이고자 한다. <br>
<br>

## 📌 주요 기능
- [x] 분실물, 습득물 등록
- [x] 유사 물품 알림
- [x] 매칭 시스템
- [x] 1:1 문의 

## ✨ 프로젝트 기대효과
- 행정복지센터 무인택배보관함을 연계하여 사용자가 분실물을 찾을 경우 만족도, 접근성 향상
- 시스템을 통해 분실물 정보를 쉽게 등록하고 검색함으로써 분실물 회수율 향상
- 전산화를 통해 관리자가 정확한 정보 제공과 신속한 대응을 함으로써 편의성, 효율성 향상
- 분실물의 신속한 회수로 인한 사회적 비용 감소

<br>

## 🙋‍♀️ 팀원
|**김나현**|**김종원**|**장현준**|**조은희**|
|:--:|:--:|:--:|:--:|
|![nh](https://github.com/beyond-sw-camp/be08-1st-2team/assets/50538268/03a3cef0-f0f9-43b3-a4e5-923ef03dcf94)|![jw](https://github.com/beyond-sw-camp/be08-1st-2team/assets/50538268/053be393-21bd-4ba1-8670-87cc03fd0efa)|![hj](https://github.com/beyond-sw-camp/be08-1st-2team/assets/50538268/87a81094-5896-409a-bd28-07286394ca15)|![eh](https://github.com/beyond-sw-camp/be08-1st-2team/assets/50538268/782bc8df-6407-42d3-9fdb-e27bcc909252)|

<br>

## ⏰ WBS
[2조 WBS 바로가기](https://docs.google.com/spreadsheets/d/1obRwcAQ55cM4DIk6DChcbbeFNfoHxEs7MsRrZOwzMGg/edit#gid=1981783699)
<br><br>

## ✏ 요구사항 정의서
[2조 요구사항 정의서 바로가기](https://docs.google.com/spreadsheets/d/1obRwcAQ55cM4DIk6DChcbbeFNfoHxEs7MsRrZOwzMGg/edit#gid=0)
<br><br>

## 📝 데이터 베이스 설계
[2조 ERD 바로가기](https://www.erdcloud.com/d/qpyT8r7NFLFYaGqGa)
<br><br>

## 🗃 테이블 명세서
[2조 테이블 명세서 바로가기](https://docs.google.com/spreadsheets/d/1obRwcAQ55cM4DIk6DChcbbeFNfoHxEs7MsRrZOwzMGg/edit#gid=598624480)
<br><br>

## DCL
```sql
GRANT ALL PRIVILEGES ON lostitems.* TO `items`@`%`;
```
<br><br>

## DDL
```sql
CREATE DATABASE lostItems;
CREATE USER `items`@`%` IDENTIFIED BY 'items';

-- 사용자 테이블 (tb_user)
CREATE TABLE tb_user (
    user_no VARCHAR(10),
    user_id VARCHAR(30) UNIQUE,
    user_pw VARCHAR(30) NOT NULL,
    user_mail VARCHAR(30) UNIQUE,
    user_tel VARCHAR(15) NOT NULL,
    user_addr VARCHAR(100) NOT NULL,
    role_no INT,
    ins_date DATE DEFAULT CURDATE(),
    upt_date DATE DEFAULT CURDATE(),
    PRIMARY KEY (user_no),
    FOREIGN KEY (role_no) REFERENCES tb_role(role_no)
);

-- 분실물 테이블(tb_lost_item)
CREATE TABLE tb_lost_item(
    l_item_no VARCHAR(10),
    l_item_name VARCHAR(100) NOT NULL,
    l_item_region VARCHAR(50) NOT NULL,
    l_item_time DATE DEFAULT CURDATE(),
    l_item_des VARCHAR(300),
    user_no VARCHAR(10) NOT NULL,
    category_no INT NOT NULL,
    region_no VARCHAR(10) NOT NULL,
    ins_date DATE DEFAULT CURDATE(),
    upt_date DATE DEFAULT CURDATE(),
    PRIMARY KEY (l_item_no),
    FOREIGN KEY (user_no) REFERENCES tb_user,
    FOREIGN KEY (category_no) REFERENCES tb_category,
    FOREIGN KEY (region_no) REFERENCES tb_region
);

-- 습득물 테이블(tb_found_item)
CREATE TABLE tb_found_item(
    f_item_no VARCHAR(10),
    f_item_name VARCHAR(100) NOT NULL,
    f_item_region VARCHAR(100) NOT NULL,
    f_item_time DATE DEFAULT CURDATE(),
    f_item_des VARCHAR(300),
    user_no VARCHAR(10) NOT NULL,
    category_no INT NOT NULL,
    region_no VARCHAR(10) NOT NULL,
    ins_date DATE DEFAULT CURDATE(),
    upt_date DATE DEFAULT CURDATE(),
    PRIMARY KEY(f_item_no),
    FOREIGN KEY(user_no) REFERENCES tb_user,
    FOREIGN KEY(category_no) REFERENCES tb_category,
    FOREIGN KEY(region_no) REFERENCES tb_region
);

-- 매칭 테이블(tb_match)
CREATE TABLE tb_match (
    match_no VARCHAR(10),
    f_item_no VARCHAR(10) NOT NULL,
    l_item_no VARCHAR(10) NOT NULL,
    match_status BOOLEAN NOT NULL DEFAULT FALSE,
    match_date DATE DEFAULT CURDATE(),
    ins_date DATE DEFAULT CURDATE(),
    upt_date DATE DEFAULT CURDATE(),
    PRIMARY KEY(match_no),
    FOREIGN KEY(f_item_no) REFERENCES tb_found_item(f_item_no),
    FOREIGN KEY(l_item_no) REFERENCES tb_lost_item(l_item_no)
);

-- 게시판 테이블 (tb_board)
CREATE TABLE tb_board (
    board_no VARCHAR(10) PRIMARY KEY,
    board_title VARCHAR(100) NOT NULL,
    board_detail VARCHAR(300) NOT NULL,
    board_type CHAR(1) NOT NULL CHECK (board_type IN ('b','r', 'n')),
    ins_date DATE DEFAULT CURDATE(),
    upt_date DATE DEFAULT CURDATE(),
    up_board_no VARCHAR(10),
    user_no VARCHAR(10) NOT NULL REFERENCES tb_user
);

-- 알림 테이블 (tb_notification)
CREATE TABLE tb_notification (
    noti_no VARCHAR(10),
    noti_date DATE DEFAULT CURDATE(),
    detail VARCHAR(300) NOT NULL,
    user_no VARCHAR(10) NOT NULL,
    match_no VARCHAR(10) NOT NULL,
    ins_date DATE DEFAULT CURDATE(),
    upt_date DATE DEFAULT CURDATE(),
    PRIMARY KEY (noti_no),
    FOREIGN KEY (user_no) REFERENCES tb_user(user_no),
    FOREIGN KEY (match_no) REFERENCES tb_match(match_no)
);

-- 지역 테이블(tb_region)
CREATE TABLE tb_region (
    region_no VARCHAR(10) PRIMARY KEY,
    sido_name VARCHAR(10),
    sigg_name VARCHAR(10),
    emd_name VARCHAR(10),
    li_name VARCHAR(10),
    ranking VARCHAR(5),
    ins_date VARCHAR(10),
    del_date VARCHAR(10),
    prev_region_no VARCHAR(10)
);

-- tb_region 인덱스 추가
CREATE INDEX idx_tb_region ON tb_region(sido_name, sigg_name, emd_name, li_name);

-- 권한 테이블(tb_role)
CREATE TABLE tb_role (
    role_no INT PRIMARY KEY,
    role_name VARCHAR(10) UNIQUE
);

-- 카테고리 테이블(tb_category)
CREATE TABLE tb_category (
    category_no INT PRIMARY KEY,
    category_name VARCHAR(20) NOT NULL
);

```
<br><br>

## DML
```sql
-- 사용자 조회
SELECT `user_id`, `user_pw`
FROM `tb_user`
WHERE `user_id` = '사용자아이디' AND `user_pw` = SHA2('사용자패스워드', 256);
```

<br><br>

## 테스트 케이스

<br><br>
