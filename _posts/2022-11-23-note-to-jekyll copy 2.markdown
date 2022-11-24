---
layout: post
title:  "리눅스 기본 명령어 조사 과제"
date:   2022-11-23 09:40:33 +0900
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

* 사용법 : ln 옵션 원본파일 대상파일

```
[vagrant@host1 bitcamp-ncp]$ ln b.txt a.txt
a.txt  b.txt  c.txt  d.txt  hello2.txt  README.md  x.txt
```
---
## mkdir (make directory)

* 디렉토리 생성
* -p 옵션을 주면 하위 디렉토리까지 한 번에 생성 가능
* 아래 예제중 ls -R 옵션은 디렉토리의 하위목록까지 전부 보여주는 옵션인데,
* 내 경우 실제로 많이 사용하진 않아서 ls 명령어에서 따로 설명하진 않았다.
* mkdir -p 옵션 예제에서 실제로 하위디렉토리가 생성되었다는 것을 보여주기 위해 사용하였다.
```
[vagrant@host1 bitcamp-ncp]$ ls
a.txt  b.txt  c.txt  d.txt  hello2.txt  README.md  x.txt
[vagrant@host1 bitcamp-ncp]$ mkdir testdir
[vagrant@host1 bitcamp-ncp]$ ls
a.txt  b.txt  c.txt  d.txt  hello2.txt  README.md  testdir  x.txt
[vagrant@host1 bitcamp-ncp]$ mkdir -p t/e/s/ts
[vagrant@host1 bitcamp-ncp]$ ls -r t/
e
[vagrant@host1 bitcamp-ncp]$ ls -r t/e/s/
ts
[vagrant@host1 bitcamp-ncp]$ ls -r t/e/
s
```
---
## mv(move)

* mv란 파일을 이동시키기 위해 사용하는 명령어
* 사용법 $ mv 파일 목적경로
* 목적 경로에 같은 이름의 파일이 존재할때 옵션 -b: 기존 파일을 백업 후, -f: 덮어쓸 것인지 묻지 않고, -i: 덮어쓸 것인지 물어보고 이동된다.
* 옵션 -v : 이동중인 상태를 표시한다 
```
[vagrant@host1 bitcamp-ncp]$ mv a.txt ~/git/bitcamp-ncp/t/
[vagrant@host1 bitcamp-ncp]$ cd t
[vagrant@host1 t]$ ls
a.txt  e
```
---
## type

* type란
* 지정된 명령어가 쉘에 내장된 명령어인지, 외부명령어인지, 앨리어스 명령어인지 등을 확인
```
[vagrant@host1 bitcamp-ncp]$ type 옵션 파일명
```
---
## which

* which 란
* 특정 명령어의 위치를 찾아주는 명령어
* -a를 옵션으로 쓸 경우 검색 가능한 모든 경로에서 해당 명령어를 찾음
```
[vagrant@host1 t]$ which find
/usr/bin/find
[vagrant@host1 t]$ which -a find
/usr/bin/find
```
---
## man (Manual Pager Utils)

* man 란
* 각종 명령어, 프로그램의 사용법을 확인함
```
[vagrant@host1 t]$
```
---
## apropos

* apropos 란?
* 지정된 키워드와 포함되어 있는 매뉴얼 페이지의 목록 정보를 출력하는 명령어로 'man -k' 명령과 동일함
```
[vagrant@host1 t]$ cd ..
[vagrant@host1 bitcamp-ncp]$ apropos b.txt
b.txt: nothing appropriate.
[vagrant@host1 bitcamp-ncp]$ apropos t
close (2)            - close a file descriptor
encrypt (3)          - encrypt 64-bit messages
environ (7)          - user environment
fclose (3)           - close a stream
fflush (3)           - flush a stream
getdomainname (2)    - get/set NIS domain name
getrlimit (2)        - get/set resource limits
hier (7)             - description of the file system hierarchy
lockf (3)            - apply, test or remove a POSIX lock on an open file
updwtmp (3)          - append an entry to the wtmp file
madvise (2)          - give advice about use of memory
mount (2)            - mount file system
rand (3)             - pseudo-random number generator

--- 이하 생략 ---
```
---
## info

* info란
* 리눅스 명령어의 사용 방법, 옵션 등을 나타냄
- 명령어 man에 비해 제공되는 명령어가 한정적
```
[vagrant@host1 bitcamp-ncp]$ info pwd
```
---
## whatis

* whatis 란
* 명령어에 대한 기능을 간략하게 나타냄
* 자세한 사용법과 설명은 man, info를 통해 확인해야함
* 완전한 키워드가 일치해야만 해당 명령어 기능을 확인할 수 있음
* whatis 데이터 베이스에서 문자열만 검색함
```
[vagrant@host1 bitcamp-ncp]$ whatis pwd
pwd (1)              - print name of current/working directory
pwd (1p)             - return working directory name
[vagrant@host1 bitcamp-ncp]$ whatis ls
ls (1)               - list directory contents
ls (1p)              - list directory contents
```
---
## alias

* alias란
* alias는 별칭이라는 뜻
* alias는 사용자가 명령어를 다른 이름으로 바꿔서 사용할 수 있는 쉘 내부 명령어를 말함
* 이 alias를 통해서 일일이 입력하기 번거로운,  길이가 긴 명령어를 간단한 이름으로 바꿔서 등록하여 업무 효율을 높일 수 있음
```
[vagrant@host1 bitcamp-ncp]$ alias
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l.='ls -d .* --color=auto'
alias ll='ls -l --color=auto'
alias ls='ls --color=auto'
alias which='alias | /usr/bin/which --tty-only --read-alias --show-dot --show-tilde'
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