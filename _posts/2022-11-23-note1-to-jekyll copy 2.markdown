---
layout: post
title:  "HTML,css 수업"
date:   2022-11-23 11:10:33 +0900
categories: jekyll update
---

* 한빛미디어에서 HTML5,css 바이블3 예제 다운로드

### HTML과 HTTP 등장 전과 후

* FTP (File Transfer Protocol)
* 시작은 논문(HTML)을 simple .txt로 만들어서 FTP server에 upload함
* 논문을 다운 받기 위해 FTP server에 접속해서 download를 함
* server에 접속해 download를 하기 위해서는 Client가 필요함
* server와 client의 데이터 송수신을 위해서 통신 규칙(protocol)이 필요함
* 단점 - 논문이 참조하는 다른 논문을 다운로드 받기 번거롭고 논문 안에 다른 논문이 업로드 된 서버 주소가 없음
* 다른 논문의 위치 정보 삽입 + .txt의 포맷을 지정(예: a href="서버/a/t.html"제 1논문/a ing src="a.gif") + 그림, 음성, 동영상 등의 삽입이 가능하게 만든 것이 HTML
* img src="a.gif" 를 데이터를 설명하는 데이터를 제어하는 데이터인 =부가데이터 , metadata, markup(출판사 용어) language의 등장 (HTML)
* 워드패드에 글을 적고 rtf로 저장 후 메모장으로 열면
* Markup 예시 (\b\f0\fs44\lang1042 ABC\'ba\'f1\'c6\'ae\'c4\'b7\'c7\'c1\'b0\'fs20\par) 
* markup을 직접 적기엔 너무 어려워 등장한 것이
* HTML(Hyper Text Markup Language)
* HTML 문서를 원활하게 받고 다른 HTML 문서를 찾아가기 쉽도록 만든 통신 프로토콜 HTTP(Hyper Text Transfer Protocol)server가 등장함
* CURL, Wget = HTTP client
* curl https://www.naver.com 을 하게되면 네이버의 화면 CMD에 출력해줌
* Wget 은 다운로드 받아줌

### HTTP Client / Server app.

* HTTP Client - 클라이언트가 먼저 요청을 함
* HTTP Server - 클라이언트의 요청에 응답 함
* HTTP Server : NginX, Apache HTTP server 가 대표적인 Server
* HTTP Client : chrome, Safari, Firefox, Edge 가 대표적인 Client
* HTTP Client의 다른 이름을 Web Browser라고 함
* HTTP Server의 다른 이름은 Web Server라고 함
* Web의 정의: 문서들이 거미줄 처럼 얽혀있다고 하여 Web이라 표현함
* HTTPS는 HTTP와 security가 합쳐져 웹(HTTP)+보안(S)라 HTTPS라 한다
---
### Web 기술의 활용

* (1세대)논문 공유 => (2세대)회사소개, 제품소개 =>(2세대) 홈페이지 => (3세대) 프로그램, 방명록, 방문자 수, 게시판 등의 기능 추가

* static resource - 정적 자원 : 작성된 그대로 유지하는 것
* CGI 규칙에 따라 작성한 프로그램
* (1)요청 -> (2)실행 -> (3)작업수행 -> (4)작업결과를 HTML, GIF, JPEG 등의 형태로 만들어 리턴 -> (5)응답

---
### full-stack 개발자 종류

* SI 신규 프로젝트 개발자
* SM 프로젝트 후 유지보수 개발자

---

### HTML의 기본 구조

* Element Tag : !docttype-html, HTML, Head, /Head, Body, /Body, /HTML
* br뒤에 / 를 넣으면 끝 Tag그 생략 표시
* Element Tag에서 생략해도 되는 Tag는 p, br 이 있음
* meta의 경우 Tag를 끝맺지 않아야 함
* 자바의 경우 대소문자를 명확히 적어야함
* HTML은 그렇지 않음
* Photoshop 을 쓰는 사람을 웹디자이너(그림,아이콘)
* HTML, CSS, JavaScript의 기본을 쓰는 사람이 웹퍼블리셔(화면)
* HTML, CSS, JavaScript, UI FrameWork를 다루는 사람을 Front-end 개발자 (Client app UI)

* Sementic

<img src="https://html.com/wp-content/uploads/html5_cheat_sheet_tags.png" alt="HTML 5 Cheat Sheets - An Infographic from " width="100%" class="infographic_embedder" /><p class="infographic_attr">Embedded from <a href="https://html.com/blog/html-5-cheat-sheets/" target="_blank"></a></p>




<br><br><br>

<div id="disqus_thread"></div>
<script>
    /**
    *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
    *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
    /*
    var disqus_config = function () {
    this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    */
    (function() { // DON'T EDIT BELOW THIS LINE
    var d = document, s = d.createElement('script');
    s.src = 'https://melonweb.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>