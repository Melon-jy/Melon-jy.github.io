---
layout: post
title:  "HTML,css 수업"
date:   2022-11-23 11:10:33 +0900
categories: jekyll update
---

# HTML, css 수업

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
* 




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