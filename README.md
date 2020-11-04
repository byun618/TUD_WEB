# TUD_WEB

## 목차
[1. 프로젝트 개요](#프로젝트-개요)     
[2. 개발 리뷰](#개발-리뷰)   
[3. 개발 환경](#개발-환경)   
[4. 개발 파트](#개발-파트)   
[5. Getting Started](#Getting-Started)

## 프로젝트 개요 (2019/10 - 2019/11)
##### fork from : https://github.com/yunobro/TUD_WEB
* 개요  
2019년 2학기 아일랜드 더블린 공과 대학([TUDublin](https://www.tudublin.ie/)), Web Development & Deployment 수업 [기말과제 프로젝트](https://github.com/yunobro/TUD_WEB/files/5480641/Pair.Project.2019.pdf). 2명이서 팀을 이뤄 진행    
* 소개  
중고거래 사이트

## 개발 리뷰
개발 난이도는 비교적 어렵지 않았으나, 생소한 PHP를 다룬다는 점에서 조금 힘든점이 있었다. 하지만 새로운 언어를 배운다는 점에서 굉장히 흥미로운 시간이였다. Team Mate 한명과 해서 2명으로 팀을 이루어서 진행하였으나, 규모가 작아 협업의 어려움은 크게 없었다. 또한, Software Engineering에서 배운 MVC 패턴을 직접 구현해 본 첫 개발이였다. 아쉬운 점은 Git에 대해 무지하던 때라 그냥 저장소 용도로만 사용한 점이 너무 아쉽다.

## 개발 환경
* [XAMPP](https://www.apachefriends.org/index.html)
    * Apache, MariaDB 그리고 PHP를 이용해 웹서버, 웹페이지 구현 및 배포
* Mac

## 개발 파트
* UI    
    * PHP를 이용한 UI 제작
* Server
    * PHP를 이용해 MVC 패턴 적용한 서버 개발
* DataBase
    * phpMyAdmin을 통해 Database 관리   
        <img width="300" alt="ezgif com-gif-maker" src="https://user-images.githubusercontent.com/27637757/97977650-e0cff580-1e0f-11eb-8b46-500fd61544e3.png">
### 내가 진행한 파트
* Database
    * member 테이블 설계
* Server
    * MVC 패턴 적용(Model View Controller)     
    ![스크린샷 2020-11-03 오후 7 52 37](https://user-images.githubusercontent.com/27637757/97976753-74082b80-1e0e-11eb-95f2-85c488e20f8d.png)
    * URL을 통해 Controller, Function 그리고 Data 전송(지금 생각해보니 위험한 방식이네;;;)  
    ```
    /TUD/public/controllername/funcname/data
    ```
    * PHP 이용해 파일 업로드 및 다운로드 구현
    * PHP로 Database 연결 및 작업

### 데모
![ezgif com-gif-maker](https://user-images.githubusercontent.com/27637757/97980390-0828c180-1e14-11eb-88d3-aa3bb995946a.gif)    
![ezgif com-gif-maker (1)](https://user-images.githubusercontent.com/27637757/97980485-33131580-1e14-11eb-9975-a27efe73feca.gif)

## Getting Started
1. [XAMPP 설치](https://www.apachefriends.org/index.html)
2. XAMPP 실행   
    2-1. General 탭에서 Start를 눌러 시작   
    <img width="581" alt="스크린샷 2020-11-03 오후 8 49 54" src="https://user-images.githubusercontent.com/27637757/97981955-6656a400-1e16-11eb-9ee2-d8a8e19496ef.png">   
    2-2. Volumnes 탭에서 Mount 클릭     
    <img width="625" alt="스크린샷 2020-11-03 오후 8 50 02" src="https://user-images.githubusercontent.com/27637757/97981961-68b8fe00-1e16-11eb-9a18-c2f2266e42e8.png">   
    2-3. Services 탭에서 Start All  
    <img width="625" alt="스크린샷 2020-11-03 오후 8 50 17" src="https://user-images.githubusercontent.com/27637757/97981959-6787d100-1e16-11eb-999d-8a17cfeb61a6.png">   
    2-4. Network 탭에서 8080 포트 Enable    
    <img width="625" alt="스크린샷 2020-11-03 오후 8 50 26" src="https://user-images.githubusercontent.com/27637757/97981926-5e96ff80-1e16-11eb-9070-d338c1e070f4.png">   
3. Git에서 클론
```
git clone https://github.com/byun618/TUD_WEB.git
```
4. Volumnes 탭에서 Mount를 했다면 `IP주소`의 이름으로 하나의 드라이브 확인 가능
**TUD** 폴더를 
```
`IP주소`/opt/lampp/htdocs
```
 경로로 복사    
 <img width="882" alt="스크린샷 2020-11-03 오후 9 05 33" src="https://user-images.githubusercontent.com/27637757/97983263-5fc92c00-1e18-11eb-8564-73ce2d00ea9c.png">
 5. 웹에서 phpMyAdmin에 접속하기 위해 아래 주소 입력
 ```
 localhost:8080/phpmyadmin
 ```
 6. Database 생성   
    6-1. **Second_market** 이라는 database 생성     
    6-2. 테이블 생성
    ```
    CREATE TABLE `member` ( `id` varchar(45) NOT NULL, `pw` varchar(45) NOT NULL, `mail` varchar(30) NOT NULL, `addr` varchar(20) NOT NULL, `city` varchar(45) NOT NULL ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
    ```

    ```
    CREATE TABLE `board` ( `board_id` int(11) NOT NULL, `title` varchar(50) NOT NULL, `content` varchar(300) NOT NULL, `author` varchar(10) NOT NULL, `date` date NOT NULL, `hit` int(11) NOT NULL, `file` varchar(100) NOT NULL ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
    ```

    ```
    CREATE TABLE `reply` ( `reply_id` int(11) NOT NULL, `board_id` int(11) NOT NULL, `author` varchar(10) NOT NULL, `content` varchar(300) NOT NULL, `date` datetime NOT NULL DEFAULT current_timestamp() ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
    ```
7. 웹페이지 접근
```
`IP주소`:8080/TUD/public
```
