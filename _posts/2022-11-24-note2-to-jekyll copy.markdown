---
layout: post
title:  "시맨틱 태그 목적과 용도"
date:   2022-11-24 18:00:33 +0900
categories: jekyll update
---
# 시맨틱 태그

* 시맨틱 태그 - 의미가 있는 태그
* 모든 block 영역은 div 태그로, inline 요소는 span 태그와 달리 header, main, footer, section, article과 같은 태그 자체에 의미가 담겨있음
* 시맨틱 태그 사용 이유 - div를 쓰면 편하지만 시맨틱 태그를 쓰는 것과 아닌 것의 차이점이 있음
* 소스코드 구조화가 쉬워짐
* 코드 가독성이 향상되어 유지보수가 쉬워짐

## nav - 네비게이션 바(메뉴) 영역에 사용하는 태그
```
<nav>
    <a href="/html/intro">HTML</a> |
    <a href="/css/intro">CSS</a> |
    <a href="/javascript/intro">JavaScript</a>
</nav>
```
<br>

## section - article 보다 큰 영역을 나타낼 때 사용함
```
<section>
    <h1>HTML</h1>
    <p>HTML(HyperText Markup Language)은 하이퍼텍스트 마크업 언어(HyperText Markup Language)라는 의미의
        웹 페이지를 위한 마크업 언어이다.</p>
</section>
<section>
    <h1>HTML의 역사</h1>
    <p>최초의 HTML은 1991년 말에 버너스리가 처음으로 인터넷에서 문서를 "HTML 태그"(HTML tag)로 부르면서 시작되었다.</p>
</section>
```
<br>

## aside - 사이드 영역에 사용하는 태그로 보통 top버튼이나 본문 영역과 별개의 내용을 포함
```
<h2>과메기</h2>
<p>과메기는 경상북도 포항 지역의 특산물로 청어나 꽁치를 추운 겨울 동안 얼렸다 녹였다를 반복하여 반건조시킨 음식이다.</p>
<aside>
    <h4>포항</h4>
    <p>포항시는 대한민국 경상북도 동해안에 위치하고 있으며, 포항시 중심을 관통하는 형산강이 영일만에 유입되면서 
        넓은 충적평야를 형성하고 있다.</p>
</aside>
```
<br>

## footer - 풋터 영역에 사용하는 태그, 회사 정보나 이메일 연락처 등이 들어있음
```
<footer>
    <p>Copyright © 2018 tcpschool.co.,Ltd. All rights reserved.</p>
    <address>Contact webmaster for more information. 070-1234-5678</address>
</footer>
```
<br>

## article - 해당 문서나 페이지 또는 사이트와는 완전히 독립적으로 구성할 수 있는 요소를 정의할때 씀

```
<article>
    <h2>2월 19일 날씨 정보</h2>
    <h3>서울</h3>
    <p>맑음</p>
    <h3>대전</h3>
    <p>흐림</p>
    <h3>부산</h3>
    <p>비</p>
</article>
```
<br>

## header - 헤더 영역에 사용하는 태그로 로고 등에 사용함
```
<article>
    <header>
        <h3>날씨 정보</h4>
        <h4>2월 19일</h4>
        <p>- 기상청 제공 -</p>
    </header>
    <p>서울 : 맑음</p>
    <p>대전 : 흐림</p>
    <p>부산 : 비</p>
</article>
```

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