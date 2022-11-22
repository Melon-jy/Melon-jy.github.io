---
layout: post
title:  "branch 다루기 수업"
date:   2022-11-22 09:40:33 +0900
categories: jekyll update
---

# VM branch

```
[vagrant@host bitcamp-ncp]git log --oneline
[vagrant@host bitcamp-ncp]file .gitignore
[vagrant@host bitcamp-ncp]less .gitignore
next page : space bar
exit : Q
[vagrant@host bitcamp-ncp]mkdir tmp
[vagrant@host tmp]touch hello.txt
[vagrant@host tmp]ls -al
[vagrant@host tmp]cd ..
[vagrant@host bitcamp-ncp]tree
[vagrant@host bitcamp-ncp]touch hello2.txt
[vagrant@host bitcamp-ncp]tree
[vagrant@host bitcamp-ncp]mkdir tmp2
[vagrant@host bitcamp-ncp]cd tmp2
[vagrant@host tmp2]touch hello3.txt
[vagrant@host tmp2]cd ..
[vagrant@host bitcamp-ncp]touch test .bak
[vagrant@host bitcamp-ncp]tree
[vagrant@host bitcamp-ncp]git status --short
[vagrant@host bitcamp-ncp]rm -rf tmp
[vagrant@host bitcamp-ncp]rm -rf tmp2
[vagrant@host bitcamp-ncp]rm *back
[vagrant@host bitcamp-ncp]ls
[vagrant@host bitcamp-ncp]tree
```

* Unix에서는 file로 다룸
* ex) 파일 -> Data, 파일 -> 디렉토리, 파일 -> 프린터 마우스 등등
* .gitignore 파일의 역할 테스트

## git diff

* CLI commands line interface 로 git diff 를 하기 힘들다


```
[vagrant@host bitcamp-ncp]nano a.txt
3333 ctrl + o enter ctrl + x
[vagrant@host bitcamp-ncp]git status --short
[vagrant@host bitcamp-ncp]git diff a.xtx
```

## git checkout [파일]

```
[vagrant@host bitcamp-ncp]git checkout b.txt
[vagrant@host bitcamp-ncp]cat b.txt
[vagrant@host bitcamp-ncp]git status --short
[vagrant@host bitcamp-ncp]nano b.txt
[vagrant@host bitcamp-ncp]cat a.txt
[vagrant@host bitcamp-ncp]cat b.txt
[vagrant@host bitcamp-ncp]git add b.txt
[vagrant@host bitcamp-ncp]git status short
[vagrant@host bitcamp-ncp]git checkout a.txt
[vagrant@host bitcamp-ncp]
```
* git checkout을 하여 unmodified 상태로 되돌리기
* 원래 저장소에 있던 상태로 되돌리는 것을 checkout이라 함
* Staging Area에 등록된 것이 없다면, 최종으로 커밋된 저장소로 돌아감



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