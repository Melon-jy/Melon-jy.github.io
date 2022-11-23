---
layout: post
title:  "오전 과제1"
date:   2022-11-22 17:40:33 +0900
categories: jekyll update
---

## 과제 목표

* 명령어 - 명령어에 대한 간단한 설명
* $명령어의 사용 예시
* 출력 결과 일부

* 예) pwd - 현재 작업 디렉토리를 표시 $ pwd = /home/vagrant

* 파일 시스템 탐색 기본 명령어
* 파일과 디렉토리 조작 명령어
* 명령어를 다루는 명령어

---

## pwd (print working directory)

* pwd 란? 현재 작업 중인 디렉토리를 나타냄
```
[vagrant@host1 bitcamp-ncp2]$ pwd
/home/vagrant/git/bitcamp-ncp2
```

---

## cd (change directory)

* cd 란? 다음 디렉토리로 이동시키며
* 절대 경로와 상대 경로로 이동이 가능함
* ..을 사용하여 이전 디렉토리로 이동 가능

```
[vagrant@host1 bitcamp-ncp2]$ cd ..
[vagrant@host1 git]$ cd bitcamp-ncp
[vagrant@host1 bitcamp-ncp]$
```

---

## ls (list)

* 디렉토리 목록을 확인할때 사용됨

```
[vagrant@host1 bitcamp-ncp]$ ls
b.txt  c.txt  d.txt  hello2.txt  README.md  x.txt 

[vagrant@host1 bitcamp-ncp]$ ls -1
b.txt
c.txt
d.txt
hello2.txt
README.md
x.txt
[vagrant@host1 bitcamp-ncp]$ ls -a
.   ..  b.txt  c.txt  d.txt  .git  .gitignore  hello2.txt  README.md  x.txt
[vagrant@host1 bitcamp-ncp]$ ls -a1
.
..
b.txt
c.txt
d.txt
.git
.gitignore
hello2.txt
README.md
x.txt
```

---

## file

* file 명령어란 지정된 파일의 종류(타입)을 확인하는 명령어
* file 명령어는 /usr/share/file 디렉토리의 magic파일을 참조하여 파일 종류를 표시해줌
* 명령어 옵션은 다음과 같음
* -c: 매직파일의 포맷을 검사하는 옵션
* -f 목록파일: 많은 파일들을 한번에 확인하기 위하여 파일 리스트인 목록 파일을 만들어서 그 안에 입력된 모든 파일을 한꺼번에 확인하는 옵션
* -m 매직파일: 지정된 매직 파일로 대상 파일을 확인함

```
[vagrant@host1 bitcamp-ncp]$ file .git
.git: directory
[vagrant@host1 bitcamp-ncp]$ file b.txt
b.txt: ASCll text
[vagrant@host1 bitcamp-ncp]$ file -f b.txt
1111: cannot open (No such file or directory)
2222: cannot open (No such file or directory)
3333: cannot open (No such file or directory)
4444: cannot open (No such file or directory)
5555: cannot open (No such file or directory)
6666: cannot open (No such file or directory)
[vagrant@host1 bitcamp-ncp]$ file -f c.txt
1111: cannot open (No such file or directory)
```
---
## less

* less 란?
* less 명령어는 more 명령어와 같이 파일의 내용을 한 화면에 보여주는 명령어
* 특징은 vi명령어와 다르게 파일 실행시 전체 파일을 읽지 않기 때문에 파일크기가 큰 파일을 빠르게 읽을 수 있음
* 명령어 사용법은 다음과 같음
* $ less 옵션 파일이름 
* 명령어 옵션으로는 -N이 있음
* less 실행중 명령어
* (Space) 줄 번호를 출력, (f) 다음 페이지로 표시, (Enter) 행 단위로 표시 (/[String])표시되는 파일에 내용 기준 이후에 내용의 문자열 찾음,  (?[string])표시되는 파일에 내용 기준 이전에 내용의 문자열을 찾음, (q)less 명령어를 종료하는 명령어

```
[vagrant@host1 bitcamp-ncp]$ less -N b.txt
```

```
1111
2222
3333
4444
5555
6666
b.txt (END)
```
---
## cp (copy)

* cp 란?
* 파일 혹은 디렉토리를 복사함
* 디렉토리를 복사하는 경우엔 -r 옵션을 주어야함
```
[vagrant@host1 bitcamp-ncp]$ ls
b.txt  c.txt  d.txt  hello2.txt  README.md  x.txt
[vagrant@host1 bitcamp-ncp]$ cp b.txt b_cp.txt
[vagrant@host1 bitcamp-ncp]$ ls
b_cp.txt  b.txt  c.txt  d.txt  hello2.txt  README.md  x.txt
[vagrant@host1 bitcamp-ncp]$ cd ..
[vagrant@host1 git]$ ls
bitcamp-ncp  bitcamp-ncp2  bitcamp-study
[vagrant@host1 git]$ cd -r bitcamp-ncp bitcamp-cp-ncp
[vagrant@host1 git]$ ls
bitcamp-cp-ncp  bitcamp-ncp  bitcamp-ncp2  bitcamp-study
```
---
## rm(remove)

* rm이란?
* 파일이나 디렉토리를 삭제할때 사용함
* 디렉토리를 삭제할때는 r 옵션을 주어야함
* -f옵션을 주면 사용자에게 삭제 여부를 묻지 않고 삭제함
* 디렉토리를 삭제할 때에는 하위 디렉토리까지 모두 삭제 되므로 주의해야함

```
[vagrant@host1 git]$ ls
bitcamp-cp-ncp  bitcamp-ncp  bitcamp-ncp2  bitcamp-study
[vagrant@host1 git]$ rm -rf bitcamp-cp-ncp
[vagrant@host1 git]$ ls
bitcamp-ncp  bitcamp-ncp2  bitcamp-study
[vagrant@host1 git]$ cd bitcamp-ncp
[vagrant@host1 bitcamp-ncp]$ ls
b_cp.txt  b.txt  c.txt  d.txt  hello2.txt  README.md  x.txt
[vagrant@host1 bitcamp-ncp]$ rm -f b.txt
b.txt  c.txt  d.txt  hello2.txt  README.md  x.txt
```
---
## ln (link)

* 심볼릭링크 (Symbolic Link)
* 단순히 원본파일을 가리키도록 링크만 시켜둔 것으로 MS의 윈도우시스템에서 흔히 사용하는 '바로가기' 같은 것이며, 원본파일을 가리키고만 있으므로 원본파일의 크기와는 무관한다. 그리고 심볼릭링크에서는 원본파일이 삭제되어 존재하지 않을 경우에 링크파일은 깜박거리면서 링크파일의 원본파일이 없다는 것을 알려준다.

* 하드링크 (Hard Link)
* 원본파일과 다른 이름으로 존재하는 동일한 파일이며 원본파일과 동일한 내용의 다른 파일이라고 할 수 있다. 그리고 하드링크에서는 원본파일과 링크파일 두개가 서로 다른 파일이기 때문에 둘 중 하나를 삭제하더라도 나머지 하나는 그대로 남아 있다. 또한 하드링크에서는 원본파일의 내용이 변경될 경우에는 링크파일의 내용 또한 자동으로 변경된다.

```

```
---
## mkdir
---
## mv
---
## type
---
## which
---
## man
---
## apropos
---
## info
---
## whatis
---
## alias
---
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