---
layout: post
title:  "웹 네트워크"
date:   2022-11-25 09:10:33 +0900
categories: jekyll update
---

# 네트워킹(NetWorking)

* connectionless - 비연결 -> 연결없이 데이터 전송 ex)편지, 방송
* subnet으로 date를 쏘면 subnet에 해당하는 모든 PC가 date를 얻을 수 있음
* TCP - 데이터 전송에 대한 신뢰
* UDP - 데이터 전송에 대한 신뢰가 없음 신뢰를 얻기 위해서는 별도의 처리가 필요함
* HTTP 1, 2version 까지는 TCP 였으나, HTTP3 이후는 UDP
* HTTP3 UDP 검색
* TCP는 Client와 Server가 3way handshake를 하는 확인 과정에서 시간이 발생하여 속도가 느림
* connection-Oritented - 연결 지향 -> 연결 후 통신 ex)전화
* Stateful - C와 S가 연결 후 계속해서 연결 요청 응답을 연결을 끊을때 까지 반복함 (다수의 Client에게 응대 불가 자원 낭비가 심함)
* stateless - 연결 요청 응답 후 연결 끊음 (많은 Client에 대응 가능)
* Stateful로 여러 Client에게 응대하기 위해 multi thread (멀티스레드)를 사용함 ssh, ftp, chatting, google meet(telnet+secure)
* HTTP5는 Stateless 방식으로 함
* 
* 
* 
* 
* 
* 
* 
* 
* 
* 
* 
* 
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