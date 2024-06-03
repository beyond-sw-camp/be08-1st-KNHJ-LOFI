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

<br>

![image](https://github.com/beyond-sw-camp/be08-1st-2go-lofi/assets/82626246/eabbd088-78c5-48fd-9850-ec817c5a3e00)

<br><br>

## ✏ 요구사항 정의서
[2조 요구사항 정의서 바로가기](https://docs.google.com/spreadsheets/d/1obRwcAQ55cM4DIk6DChcbbeFNfoHxEs7MsRrZOwzMGg/edit#gid=0)

<br>

![image](https://github.com/beyond-sw-camp/be08-1st-2go-lofi/assets/82626246/ceb81f56-b9ba-43f6-9bda-49826f43da6c)
<br><br>

## 📝 데이터 베이스 설계
[2조 ERD 바로가기](https://www.erdcloud.com/d/qpyT8r7NFLFYaGqGa)

<br>

![프로젝트](https://github.com/beyond-sw-camp/be08-1st-2go-lofi/assets/82626246/ca7661cf-49f5-471c-b697-b6e3bf80fea9)
<br><br>

## 🗃 테이블 명세서
[2조 테이블 명세서 바로가기](https://docs.google.com/spreadsheets/d/1obRwcAQ55cM4DIk6DChcbbeFNfoHxEs7MsRrZOwzMGg/edit#gid=598624480)

<br>

![image](https://github.com/beyond-sw-camp/be08-1st-2go-lofi/assets/82626246/d264c4e2-fff1-4bd0-a473-93bb2ba9ea92)

![image](https://github.com/beyond-sw-camp/be08-1st-2go-lofi/assets/82626246/fd8dd094-e8ab-42e7-aeef-ebe5dd8328e7)

![image](https://github.com/beyond-sw-camp/be08-1st-2go-lofi/assets/82626246/d6d383c4-6e21-4571-89b0-1712da14b9de)

![image](https://github.com/beyond-sw-camp/be08-1st-2go-lofi/assets/82626246/e0bc38a2-0da7-441e-9610-f11975e38ac3)

![image](https://github.com/beyond-sw-camp/be08-1st-2go-lofi/assets/82626246/a8e3a6c8-a0f8-40e9-adb9-03eed42a6993)

<br>

## 📎 지역 데이터
[전국 법정동 csv 파일 링크](https://www.data.go.kr/data/15063424/fileData.do)


<br><br>

## ⌨️ SQL

<details>
<summary>DCL</summary>

- **DB 사용자 권한 부여**
  <details>
  <summary>SQL</summary>
  
  ```sql
  GRANT ALL PRIVILEGES ON lostitems.* TO `items`@`%`;
  ```
  </details>
</details>

<details>
<summary>DDL</summary>

- **DB 생성 및 테이블 생성**
  <details>
  <summary>SQL</summary>
  
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
      FOREIGN KEY(f_item_no) REFERENCES tb_found_item(f_item_no)
      DELETE ON CASCADE,
      FOREIGN KEY(l_item_no) REFERENCES tb_lost_item(l_item_no)
      DELETE ON CASCADE
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
      user_no VARCHAR(10) NOT NULL,
      FOREIGN KEY(user_no) REFERENCES tb_user
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
      DELETE ON CASCADE
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
  CREATE INDEX idx_tb_region
  ON tb_region(sido_name, sigg_name, emd_name, li_name);
  
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
  </details>
- **트리거, 함수, 프로시저, 이벤트 생성**
    <details><summary>트리거
  </summary>

  - **분실물이 등록된 경우 알림 전송 트리거**
    <details><summary>SQL
    </summary>
        
    ```sql
    DELIMITER $$
    CREATE OR REPLACE TRIGGER trg_match_loit
    AFTER INSERT ON tb_lost_item
    FOR EACH ROW
    BEGIN
        DECLARE f_cnt INT;
    
        SELECT COUNT(f_item_no) INTO f_cnt
        FROM tb_found_item
        WHERE region_no LIKE CONCAT(SUBSTRING(NEW.region_no, 1, 4), '%')
          AND category_no = NEW.category_no;
    
        IF f_cnt >= 1 THEN
            INSERT INTO tb_match (match_no, f_item_no, l_item_no)
            SELECT GET_NO('tb_match'),
                   f_item_no,
                   NEW.l_item_no
            FROM tb_found_item
            WHERE region_no LIKE CONCAT(SUBSTRING(NEW.region_no, 1, 4), '%')
              AND category_no = NEW.category_no;
        END IF;
    
    END$$
    DELIMITER ;
    ```
    </details>
  - **습득물이 등록된 경우 알림 전송 트리거**
    <details><summary>SQL
    </summary>
        
    ```sql
    DELIMITER $$
    CREATE OR REPLACE TRIGGER trg_match_fdit
    AFTER INSERT ON tb_found_item
    FOR EACH ROW
    BEGIN
        DECLARE l_cnt INT;
    
        SELECT COUNT(l_item_no) INTO l_cnt
        FROM tb_lost_item
        WHERE region_no LIKE CONCAT(SUBSTRING(NEW.region_no, 1, 4), '%')
          AND category_no = NEW.category_no;
    
        IF l_cnt >= 1 THEN
            INSERT INTO tb_match (match_no, f_item_no, l_item_no)
            SELECT GET_NO('tb_match'),
                   NEW.f_item_no,
                   l_item_no
            FROM tb_lost_item
            WHERE region_no LIKE CONCAT(SUBSTRING(NEW.region_no, 1, 4), '%')
              AND category_no = NEW.category_no;
        END IF;
    
    END$$
    DELIMITER ;
    ```
    </details>
  </details>

  <details><summary>함수
  </summary>

  - **기간 만료 물품 삭제 이벤트**
    <details><summary>SQL
    </summary>
    
    ```sql
    BEGIN
    	DECLARE v_prefix VARCHAR(10);
     	DECLARE v_hypen CHAR(1);
     	DECLARE v_formmater INT;
    	DECLARE v_no VARCHAR(30);
    	
    	-- id 규칙 가져오기
    	SELECT PREFIX, hypen_yn, formmater 
    	INTO v_prefix, v_hypen, v_formmater
    	FROM auto_no
    	WHERE TABLE_NAME = tb_name;
    	
    	-- 가져온 값으로 insert update
    	INSERT INTO auto_no_dtl
    	(TABLE_NAME, PREFIX, hypen_yn, formmater)
    	VALUES
    	(tb_name, v_prefix, v_hypen, v_formmater)
    	ON DUPLICATE KEY
    	UPDATE SEQUENCE = SEQUENCE + 1;
    	
    	SELECT CONCAT(PREFIX, if(hypen_yn = 'Y', '-', ''), LPAD(SEQUENCE, 8, '0')) INTO v_NO
    	FROM auto_no_dtl
    	WHERE TABLE_NAME = tb_name
    	  AND PREFIX = v_prefix
    	  AND hypen_yn = v_hypen
    	  AND formmater = v_formmater;
    
    	RETURN v_no;
    END
    ```
    </details>
  </details>
  
  <details><summary>프로시저
  </summary>

  - **180일 지난 습득물 삭제 프로시저**
    <details><summary>SQL
    </summary>
    
    ```sql
    DELIMITER $$
    CREATE OR REPLACE PROCEDURE delFdProc ()
    BEGIN
          INSERT INTO tb_recyclebin(
          rb_no, delete_tpye, f_item_name, f_item_region, f_item_time, f_item_des, f_user_no, f_category_no, f_region_no
          ) SELECT
          GET_NO('tb_recyclebin') , 'PE', A.f_item_name, A.f_item_region, A.f_item_time, A.f_item_des, A.user_no, A.category_no, A.region_no
          FROM tb_found_item A
          LEFT OUTER JOIN
            (SELECT fi.l_item_no
             FROM tb_found_item fi
             LEFT OUTER JOIN tb_match m ON m.f_item_no = li.f_item_no
             WHERE 1=1
               AND m.match_status = TRUE ) B ON B.f_item_no = A.f_item_no
          WHERE 1=1
            AND A.ins_date <= subDATE(CURDATE(), 180)
            AND A.upt_date <= subDATE(CURDATE(), 180)
            AND B.f_item_no IS NULL;
    
          DELETE A FROM tb_found_item A
          LEFT JOIN (
              SELECT fi.l_item_no
              FROM tb_found_item fi
              LEFT JOIN tb_match m ON m.l_item_no = fi.l_item_no
              WHERE m.match_status = TRUE
          ) B ON B.f_item_no = A.f_item_no
          WHERE A.ins_date <= SUBDATE(CURDATE(), 180)
            AND A.upt_date <= SUBDATE(CURDATE(), 180)
            AND B.f_item_no IS NULL;
    END $$
    DELIMITER ;
    ```
    </details>
  - **180일 지난 분실물 삭제 프로시저**
    <details><summary>SQL
    </summary>
    
    ```sql
    DELIMITER $$
    CREATE OR REPLACE PROCEDURE delLiProc ()
    BEGIN
          INSERT INTO tb_recyclebin(
          rb_no, delete_tpye, l_item_name, l_item_region, l_item_time, l_item_des, l_user_no, l_category_no, l_region_no
          ) SELECT
          GET_NO('tb_recyclebin') , 'PE', A.l_item_name, A.l_item_region, A.l_item_time, A.l_item_des, A.user_no, A.category_no, A.region_no
          FROM tb_lost_item A
          LEFT OUTER JOIN
            (SELECT li.l_item_no
             FROM tb_lost_item li
             LEFT OUTER JOIN tb_match m ON m.l_item_no = li.l_item_no
             WHERE 1=1
               AND m.match_status = TRUE ) B ON B.l_item_no = A.l_item_no
          WHERE 1=1
            AND A.ins_date <= subDATE(CURDATE(), 180)
            AND A.upt_date <= subDATE(CURDATE(), 180)
            AND B.l_item_no IS NULL;
    
          DELETE FROM tb_lost_item A, B
          LEFT OUTER JOIN
            (SELECT li.l_item_no
             FROM tb_lost_item li
             LEFT OUTER JOIN tb_match m ON m.l_item_no = li.l_item_no
             WHERE 1=1
               AND m.match_status = TRUE ) B ON B.l_item_no = A.l_item_no
          WHERE 1=1
            AND A.ins_date <= subDATE(CURDATE(), 180)
            AND A.upt_date <= subDATE(CURDATE(), 180)
            AND B.l_item_no IS NULL;
    END $$
    DELIMITER ;
    ```
    </details>
  </details>

    <details><summary>이벤트
  </summary>

  - **기간 만료 물품 삭제 이벤트**
    <details><summary>SQL
    </summary>
    
    ```sql
    CREATE OR REPLACE EVENT item_expiration
        ON SCHEDULE EVERY 1 DAY
        STARTS '2024-05-31 00:10:00'
        COMMENT '매일 1회 0시 10분에 실행하는 프로시저'
        DO
        BEGIN
          CALL delLiProc();
          CALL delFdProc();
        END$$
    DELIMITER ;
    ```
    </details>
  </details>
</details>

<br><br>

## 💡 테스트 케이스
[테스트 케이스 바로가기](https://docs.google.com/spreadsheets/d/1obRwcAQ55cM4DIk6DChcbbeFNfoHxEs7MsRrZOwzMGg/edit#gid=1143330171)
<br><br>
![image](https://github.com/beyond-sw-camp/be08-1st-2go-lofi/assets/82626246/2d029ea0-d646-4d88-84c6-06116f11f84b)

<details><summary>DML
</summary>

- **테스트 분류**
  <details><summary>1. 사용자
  </summary>

  - **가입**
    <details><summary>SQL
    </summary>
    
    ```sql
    INSERT INTO tb_user
    VALUES ('사용자 번호', '사용자 이름', '사용자 아이디', '사용자 비밀번호', '사용자 이메일', '전화번호', '지역', 권한번호, DEFAULT, DEFAULT);
    ```
    </details>
  - **로그인**
    <details><summary>SQL
    </summary>
    
    ```sql
    SELECT `user_id`, `user_pw`
    FROM tb_user
    WHERE `user_id` = '사용자 아이디' AND `user_pw` = SHA2('사용자 비밀번호', 256);
    ```
    </details>
  - **아이디 찾기**
    <details><summary>SQL
    </summary>
    
    ```sql
    SELECT `user_id`,
            `user_mail`
    FROM tb_user
    WHERE `user_mail` = '사용자 이메일';
    ```
    </details>
  - **비밀번호 찾기/변경**
    <details><summary>비밀번호 찾기/변경
    </summary>
    
    ```sql
    UPDATE tb_user
    SET `user_pw` = SHA2('변경 할 비밀번호', 256)
    WHERE `user_pw` = (
    	SELECT `user_pw` 
    	FROM `tb_user`
    	WHERE `user_id` = '사용자 아이디' 
    	  AND `user_mail` = '사용자 이메일'
    	  AND `user_tel` = '사용자 전화번호');
    ```
    </details>
  - **사용자 정보 조회**
    <details><summary>SQL
    </summary>
    
    ```sql
    SELECT `user_name`, `user_mail`, `user_tel`, `user_addr`
    FROM tb_user
    WHERE `user_id` = '사용자 아이디' AND `user_pw` = SHA2('사용자 비밀번호', 256);
    ```
    </details>
  - **문의**
    <details><summary>SQL
    </summary>
    
    ```sql
    INSERT INTO tb_board
    VALUES ('문의 번호', '제목', '내용',
     'b', DEFAULT, DEFAULT, NULL, '사용자 번호');
    ```
    </details>
  - **탈퇴**
    <details><summary>SQL
    </summary>
    
    ```sql
    DELETE
    FROM tb_user
    WHERE `user_id` = '사용자 아이디' 
      AND `user_pw` = SHA2('사용자 비밀번호', 256)
      AND `user_email` = '사용자 이메일';
    ```
    </details>
  </details>
  
  <details><summary>2. 관리자
  </summary>

  - **매칭 상태 변경**
    <details><summary>SQL
    </summary>
    
    ```sql
    UPDATE tb_match
    SET match_status = 1
    WHERE match_no = '매칭 번호'
      AND user_no = '사용자 번호';
    ```
    </details>
  - **카테고리 정보 등록**
    <details><summary>SQL
    </summary>
    
    ```sql
    INSERT INTO tb_category
    VALUES (카테고리 번호, '카테고리 이름');
    ```
    </details>
  - **공지 사항 등록**
    <details><summary>SQL
    </summary>
    
    ```sql
    INSERT INTO tb_board
    VALUES (GET_NO(tb_board), '제목', '내용',
     'n', DEFAULT, DEFAULT, NULL, '관리자 번호');
    ```
    </details>
  - **공지 사항 삭제**
    <details><summary>SQL
    </summary>
    
    ```sql
    DELETE
    FROM tb_board
    WHERE board_no = '공지사항 번호';
    ```
    </details>
  - **공지 사항 수정**
    <details><summary>SQL
    </summary>
    
    ```sql
    UPDATE tb_board
    SET '수정 할 컬럼' = '수정 할 내용'
    WHERE board_no = '공지사항 번호';
    ```
    </details>
  - **지역 정보 등록**
    <details><summary>SQL
    </summary>
    
    ```sql
    INSERT INTO tb_region
    VALUES ('지역 번호', '시, 도', '시, 구', '동, 면', '리', 'ranking', '등록 날짜');
    ```
    </details>
  - **지역 정보 삭제**
    <details><summary>SQL
    </summary>
    
    ```sql
    DELETE
    FROM tb_region
    WHERE region_no = '지역 번호';
    ```
    </details>
  - **지역 정보 수정**
    <details><summary>SQL
    </summary>
    
    ```sql
    UPDATE tb_region
    SET '수정 할 컬럼' = '수정 할 내용'
    WHERE region_no = '지역 번호';
    ```
    </details>
  - **문의글에 대한 답변**
    <details><summary>SQL
    </summary>
    
    ```sql
    INSERT INTO tb_board
    VALUES ('문의 답변 번호', '제목', '내용',
     'r', DEFAULT, DEFAULT, '문의글 번호', '관리자 번호');
    ```
    </details>
  - **분실물 통계**
    <details><summary>SQL
    </summary>
    
    ```sql
    -- a : 분실물 등록된 갯수
    SELECT COUNT(*)
    FROM tb_lost_item;
    
    -- b : 등록된 분실물 중 매칭이 성공된 것
    SELECT COUNT(*)
    FROM tb_lost_item l
    LEFT OUTER JOIN tb_match m ON m.l_item_no = l.l_item_no
    WHERE m.match_status = TRUE;
    
    -- c : 매칭이 성공이후 사용자 인계까지 이루어진 분실물
    SELECT COUNT(*)
    FROM tb_recyclebin
    WHERE delete_tpye = 'MS';
    
    /*
     분실물 통계 = b + c / a + c
    */
    ```
    </details>
  </details>
  
  <details><summary>3. 분실물
  </summary>
    
  - **분실물 등록**
    <details><summary>SQL
    </summary>
    
    ```sql
    INSERT INTO tb_lost_item 
    VALUES (GET_NO('분실물 번호'), '분실물 이름', 분실 장소', '분실 시간', '설명',
                분실물 등록일자', '분실물 수정일자', '사용자 번호', '카테고리 번호', '지역 번호');
    ```
    </details>
  - **분실물 검색**
    <details><summary>SQL
    </summary>
    
    ```sql
    SELECT lost.*
    FROM tb_lost_item lost
    INNER JOIN tb_region region ON lost.region_no = region.region_no
    INNER JOIN tb_category cate ON lost.category_no = cate.category_no
    WHERE lost.category_no = '카테고리 번호' 
    AND lost.category_no = cate.category_no
    AND lost.region_no = region.region_no;
    ```
    </details>
  - **분실물 수정**
    <details><summary>SQL
    </summary>
    
    ```sql
    UPDATE tb_lost_item
    INNER JOIN tb_user `user` ON lost.user_no = `user`.user_no
    SET l_item_name = '수정할 수집품 이름',
         l_item_region = '수정할 수집품 장소',
         l_item_des = '수정할 수집품 설명'
    WHERE user_id = '사용자 아이디' AND l_item_no = '분실물 번호';
    ```
    </details>
  - **분실물 삭제**
    <details><summary>SQL
    </summary>
    
    ```sql
    DELETE
    FROM tb_lost_item
    WHERE l_item_no IN (
        SELECT li.l_item_no
        FROM tb_lost_item li
        LEFT OUTER JOIN tb_match m ON li.l_item_no = m.l_item_no
        WHERE m.match_status = 0
          AND li.l_item_no = '분실물 번호');
    ```
    </details>
  - **나의 분실물 조회**
    <details><summary>SQL
    </summary>
    
    ```sql
    SELECT lost.*
    FROM tb_lost_item lost
    INNER JOIN tb_user `user` ON lost.user_no = `user`.user_no
    WHERE `user`.user_id = '사용자 아이디'
    ORDER BY lost.ins_date DESC; 
    ```
    </details>
  </details>
  
  <details><summary>4. 습득물
  </summary>

  - **습득물 등록**
    <details><summary>SQL
    </summary>
    
    ```sql
    INSERT INTO tb_lost_item
    VALUES ('습득물 번호',
                '습득물 이름',
                '습득 장소',
                '습득 시간',
                '설명',
                '습득물 등록일자',
                '습득물 수정일자',
                '사용자 번호',
                '카테고리 번호',
                '지역 번호');
    ```
    </details>
  - **습득물 조회**
    <details><summary>SQL
    </summary>
    
    ```sql
    SELECT f.*
    FROM tb_found_item f
    INNER JOIN tb_category c ON f.category_no = c.category_no
    INNER JOIN tb_region r ON f.region_no = r.region_no
    WHERE category_name = '카테고리 이름' OR sido_name = '시도명';
    ```
    </details>
  - **습득물 수정**
    <details><summary>SQL
    </summary>
    
    ```sql
    UPDATE tb_found_item f
    INNER JOIN tb_user u ON f.user_no = u.user_no 
    SET f_item_name = '수정할 습득물 이름',
         f_item_region = '수정할 습득 장소',
         f_item_des = '수정할 습득물 상세정보내용',
         ins_date = '수정한 날짜';
    ```
    </details>
  - **습득물 삭제**
    <details><summary>SQL
    </summary>
    
    ```sql
    DELETE
    FROM tb_found_item
    WHERE f_item_no IN (
        SELECT f.f_item_no
        FROM tb_fount_item f
        LEFT OUTER JOIN tb_match m ON f.f_item_no = m.f_item_no
        WHERE m.match_status = 0
          AND fi.f_item_no = '분실물 번호');
    ```
    </details>
  - **나의 습득물 조회**
    <details><summary>SQL
    </summary>
    
    ```sql
    SELECT f.*, user_id
    FROM tb_found_item f
    INNER JOIN tb_user u ON f.user_no = u.user_no
    WHERE user_id = '사용자 아이디';
    ```
    </details>
  </details>
</details>

</details>

<br><br>

## 🕯 회고
| 이름 | 내용 |
| :----: | :----- |
| 김나현 &nbsp;&nbsp; | 실습으로 가벼운 것들만 진행하다가 직접 데이터 베이스를 활용할 수 있어 좋은 경험이 될 수 있었다. <br> 팀원들과 함께 진행하여 헷갈리거나 모르는 점도 도와가며 팀원들에게 배울 수 있어서 좋았다. <br> 짧은 기간동안 함께 잘 이끌어준 팀원들에게 정말 고맙고 재미있었다고 말해주고 싶다! |
| 김종원 &nbsp;&nbsp; | 처음 만난 팀원들과 좋은 팀워크로 프로젝트를 마무리 한 것 같아 좋았고 팀원들 모두 열심히 잘해줘서 <br> 결과도 만족스러웠습니다. 이 프로젝트를 통해 DB 설계에 대한 자신감이 생겼고 <br> 여러 서비스에 대한 DB를 생각해 볼 수 있는 경험이었습니다. 그리고 짧지 않던 시간동안 고생해준 팀원들에게 고마웠습니다. |
| 장현준 &nbsp;&nbsp; | 기존에는 oracle만 써봐서 mysql 문법은 좀 어색했지만 쓰다보니 둘 사이 유사한 점이 많아서 어렵지 않게 적응할 수 있었다. <br> 그리고 이번 프로젝트를 하면서 수업시간에 배운 것을 다시 공부하고, 사용해보면서 mysql문법에 많이 익숙해진 것 같다. <br> 무엇보다 팀원 모두 적극적으로 참여해주고, 의견을 제시하면서도 충돌없이 프로젝트를 마무리해서 고마웠습니다. |
| 조은희 &nbsp;&nbsp; | 처음부터 설계를 완벽하게 하고 싶었지만 실제로 DB를 생성하고 이벤트, 트리거를 만들다보니 변경사항이 생길 수 밖에 없었고 <br> 어떻게 하면 더 효율적으로 관리할 수 있을지 고민을 많이 했기에 다음 프로젝트에 도움이 많이 될 것 같습니다. <br> 또한 짧은 기간이었지만 조원들이 잘 따라와줘서 프로젝트를 수월하게 진행할 수 있었습니다 ! 다들 감사합니다 😉 |
