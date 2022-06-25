---
title: "프로젝트 인터뷰 준비"
excerpt: "프로젝트 인터뷰 준비"
categories:
  - interview
tags:
  - [interview]
toc: true
toc_sticky: true
date: 2022-04-02
last_modified_at: 2022-04-02
---

1. 토큰 기반 인증 서비스 구현
   
   Spring Security와 JWT를 활용하여 구현하였으며, Security부분의 경우 리소스 별 범위를 성정하였으며, 인증 오류 시 핸들러를 통해 Error페이지로 이동하도록 설정하였습니다. CORS 설정은 특정 Origins에만 자원 공유를 허가하였습니다. JWT라이브러리를 추가하여 기존 폼에 Claims를 활용하여 사용자 정보를 추가 및 재로그인 시 Update, 로그아웃 시 초기화하였습니다.
<br><br>

2. 서버, 클라이언트간 HTTP 프로토콜 REST 아키텍처 적용
   
   Spring MVC 프레임워크에 @RestController을 사용하여 @ResponseBody를 추가할 필요가 없이 데이터를 JSON/XML형식의 HTTP 응답을 직접 작성하여 클라이언트에게 보내는 아키텍처를 적용하였습니다.
<br><br>

3. Database Table 논리적/물리적 구조 설계
   
   관계형 데이터베이스로써 논리적 구조 설계 시 논리적 스키마 설계 및 트랜잭션 인터페이스를 설계하였으며, 물리적 구조 설계 시 내부 metestream을 통한 데이터 구조화를 실시한 후 DBMS DDL 작성 후 DBA에게 전달
<br><br>

4. nginx 설치 및 SSL, TLS, proxy_pass 적용
   
   원하는 경로에 설치하기 위해 make를 활용하여 컴파일 설치하였으며 conf파일 설정을 통해 SSL경로, proxy_pass 설정을 하여 로드벨런싱 구현하였습니다.
   추가적으로 location 정보 설정을 통해 초기 경로 및 error 페이지 설정하였습니다.
<br><br>

5. 생산성 향상 및 배포 안정성을 위한 자동화
   
   GitLab setting CI/DI Runner를 활용하여 배포 서버 등록 및 Repository master의 경우 자동 배포 지원
<br><br>

6. User Daily Rolling File 로그모니터링 구현
   
   Sift4j를 활용하여 로그인 정보 중 key값을 설정 후 file 설정 및 pattern설정을 통해 user별 로그모니터링 구현
<br><br>

7. axios request / response 비동기 처리
   
   Promise API를 활용하는 HTTP 비동기 통신 라이브러리입니다.
<br><br>

8. node.js build, start 구현
   
   create-react-app을 통해 기본 폼을 다운받았습니다. 빌드의 경우 Webpack을 통해 다수의 js파일을 하나의 js로 압축하여 컴파일, 정보은닉에 도움을 받았습니다. start의 경우 WebpackDevServer 객체를 이용하여 실시간 리로딩 환경을 구현하였습니다.
<br><br>

9. 인터페이스 충돌 방지 Private Module Pattern 적용
    
    자주 사용되는 기능의 경우 인터페이스를 만들어두거나 혹은 별도의 함수로 만들어 어떤 메게변수가 들어오더라도 동일간 동작을 하게 구현하였습니다.
<br><br>

10. 빠른 개발, 재사용성을 고려한 JSTL Core Tag 활용
    
    주로 core를 활용하여 body영역에 변수 지원, 흐름 제어에 주로 사용하였습니다.
<br><br>

11. Hudson, Jenkins 원버튼 배포 시스템 자동화
    
    Repository URL 설정 및 svn 인스턴스 설정을 통해 원버튼 배포 시스템 구현 및 자동 배포 조건 설정을 통해 자동화 구현
<br><br>

12. Image 2중하 서버 저장을 위해 Symbolic link 적용
    
    파일 업로드 시 2중화된 web서버에 등록하기 보다는 하나의 서버에 업로드라여 참조하는 방법을 고려하여 구현하였습니다. 심볼릭 링크의 경우 리눅스 기반 ln 명령어를 활용하여 구현하였습니다.
<br><br>

13. html2canvas란?
    
    javascript상에 html2canvas를 활용하여 화면 캡쳐, base64를 통해 img태그 옵션 중 src안에 넣어 다운로드 및 공유기능을 구현하였습니다.
<br><br>

14. 3rd party library 활용
    
    효율적이고 빠른 개발을 위해 휴대폰/카드/공동 인증 서비스, 가상키보드, 실명인증 3rd party library를 활용하였습니다.
<br><br>

15. 패킷 스니핑 및 웹 프록시 도구 이용한 정보 평문 노출 방지
    
    평문 데이터 노출을 방지하기위해 nginx location에 ssl 경로 추가 및 ssl 인증 발급 받아 경로에 추가하는 작업을 하였습니다.
<br><br>
   
16. 웹 서버 및 오류 메시지를 통한 운영정보 노출 방지
    
    운영정보 노출 방지를 위해
<br><br>

17. Cookie Securre HttpOnly 설정
    
    jeus의 경우 JUESMAIN.xml에 secure 설정 및 HttpOnly 체크 로직 추가하였습니다.
    nginx의 경우 proxy_cookie_path내 secure; httpOnly 체크 로직 추가하였습니다.
