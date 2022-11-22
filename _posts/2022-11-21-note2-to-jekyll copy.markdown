---
layout: post
title:  "branch 다루기 수업"
date:   2022-11-22 09:40:33 +0900
categories: jekyll update
---

# VM branch

* 소프트웨어를 개발할 때에 개발자들은 동일한 소스코드를 함께 공유하고 다루게 됩니다. 동일한 소스코드 위에서 어떤 개발자는 버그를 수정하기도 하고 또 다른 개발자는 새로운 기능을 만들어 내기도 하죠. 이와 같이 여러 사람이 동일한 소스코드를 기반으로 서로 다른 작업을 할 때에는 각각 서로 다른 버전의 코드가 만들어 질 수 밖에 없습니다.

* 이럴 때, 여러 개발자들이 동시에 다양한 작업을 할 수 있게 만들어 주는 기능이 바로 '브랜치(Branch)' 입니다. 각자 독립적인 작업 영역(저장소) 안에서 마음대로 소스코드를 변경할 수 있지요. 이렇게 분리된 작업 영역에서 변경된 내용은 나중에 원래의 버전과 비교해서 하나의 새로운 버전으로 만들어 낼 수 있습니다.

<img src="https://github.com/Melon-jy/Melon-jy.github.io/blob/main/baranch1.png?raw=true" width="400">


<img src="https://github.com/Melon-jy/Melon-jy.github.io/blob/main/branch2.png?raw=true" width="400">



[이미지 출처]("https://backlog.com/git-tutorial/kr/stepup/stepup1_1.html")
```
[vagrant@host bitcamp-ncp]sudo yum install http://opensource.wandisco.com/centos/7/git/x86_64/wandisco-git-release-7-1.noarch.rpm
[vagrant@host bitcamp-ncp]sudo yum remove git
[vagrant@host bitcamp-ncp]sudo yum install git
[vagrant@host bitcamp-ncp]git --version
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
[vagrant@host bitcamp-ncp]cat a.txt
[vagrant@host bitcamp-ncp]can b.txt
[vagrant@host bitcamp-ncp]git checkout b.txt
[vagrant@host bitcamp-ncp]cat b.txt
```
* git checkout을 하여 unmodified 상태로 되돌리기
* 원래 저장소에 있던 상태로 되돌리는 것을 checkout이라 함
* Staging Area에 등록된 것이 없다면, 최종으로 커밋된 저장소로 돌아감
* 작업 디렉토리에 파일을 변경한 후 변경 전으로 되돌리는 것이 checkout
* git add(staging area)를 하게되면 이미 넘긴 상태라 checkout으로 되돌릴 수 없음


```
[vagrant@host bitcamp-ncp]nano b.txt
[vagrant@host bitcamp-ncp]git status --short
[vagrant@host bitcamp-ncp]cat b.txt
[vagrant@host bitcamp-ncp]git checkout b.txt
[vagrant@host bitcamp-ncp]cat b.txt
[vagrant@host bitcamp-ncp]git log --oneline --graph --all

```

### HEAD와 Branch

* 서버 저장소 Main Branch : server에 푸쉬할 때마다 1번 저장소에서 4번 저장소로 HEAD(작업Branch)가 넘어감
* add를 해서 checkout이 안될 경우 reset을 통해 HEAD상태로 되돌린 후 checkout을 할 수 있음

```
[vagrant@host bitcamp-ncp]git status --short
[vagrant@host bitcamp-ncp]cat b.txt
[vagrant@host bitcamp-ncp]git reset HEAD b.txt
[vagrant@host bitcamp-ncp]git status --short
[vagrant@host bitcamp-ncp]git checkout b.txt
[vagrant@host bitcamp-ncp]cat b.txt
```

## git 원격 저장소 정보 출력

```
[vagrant@host bitcamp-ncp]git remote -v
[vagrant@host bitcamp-ncp]git remote show origin
[vagrant@host bitcamp-ncp]git add .
[vagrant@host bitcamp-ncp]git commit -m "11"
[vagrant@host bitcamp-ncp]git log --oneline --graph --all
[vagrant@host bitcamp-ncp]git push
```

## host2 사용

```
[vagrant@host2 bitcamp-ncp]git pull
[vagrant@host1 bitcamp-ncp]nano a.txt
[vagrant@host1 bitcamp-ncp]git log --oneline --graph --all
[vagrant@host2 bitcamp-ncp]git fetch
[vagrant@host2 bitcamp-ncp]
```

## git merge [브랜치 이름]

* 현재 브랜치의 커밋에 다른 브랜치의 커밋 내용을 합친다.

### Fast-Forward

* merge가 단순할 경우엔 Fast Forward가 쉽다.
* 로컬에 있는 이전 버전이 서버의 버전 순서와 같을 경우 합치기 쉽다.
* 그대로 이어 붙히고 HEAD를 마지막 version으로 이동시키면 된다.

```
[vagrant@host2 bitcamp-ncp]git merge
[vagrant@host1 bitcamp-ncp]nano a.txt
[vagrant@host1 bitcamp-ncp]git add .
[vagrant@host1 bitcamp-ncp]git commit -m "13"
[vagrant@host1 bitcamp-ncp]git push
[vagrant@host1 bitcamp-ncp]nano a.txt
[vagrant@host1 bitcamp-ncp]git add .
[vagrant@host1 bitcamp-ncp]git commit -m "14"
[vagrant@host1 bitcamp-ncp]git push
[vagrant@host1 bitcamp-ncp]nano a.txt
[vagrant@host1 bitcamp-ncp]git add .
[vagrant@host1 bitcamp-ncp]git commit -m "15"
[vagrant@host1 bitcamp-ncp]git push
[vagrant@host1 bitcamp-ncp]nano a.txt
[vagrant@host1 bitcamp-ncp]git add .
[vagrant@host1 bitcamp-ncp]git commit -m "16"
[vagrant@host1 bitcamp-ncp]git push
[vagrant@host2 bitcamp-ncp]git fetch
[vagrant@host2 bitcamp-ncp]git log --oneline --graph --all
[vagrant@host2 bitcamp-ncp]git merge
[vagrant@host2 bitcamp-ncp]git log --oneline --graph --all
```


```
[vagrant@host1 bitcamp-ncp]nano b.txt
[vagrant@host1 bitcamp-ncp]git add .
[vagrant@host1 bitcamp-ncp]git commit -m "17"
[vagrant@host1 bitcamp-ncp]nano b.txt
[vagrant@host1 bitcamp-ncp]git add .
[vagrant@host1 bitcamp-ncp]git commit -m "18"
[vagrant@host1 bitcamp-ncp]git log --oneline --graph --all
[vagrant@host1 bitcamp-ncp]git push
```

* Fast Forward가 발생하지 않는 경우

```
[vagrant@host2 bitcamp-ncp]nano a.txt
[vagrant@host2 bitcamp-ncp]git add .
[vagrant@host2 bitcamp-ncp]git commit -m "19"
[vagrant@host2 bitcamp-ncp]nano a.txt
[vagrant@host2 bitcamp-ncp]git add .
[vagrant@host2 bitcamp-ncp]git commit -m "20"
[vagrant@host2 bitcamp-ncp]git log --oneline --graph --all
[vagrant@host2 bitcamp-ncp]git fetch
[vagrant@host2 bitcamp-ncp]git log --oneline --graph --all
[vagrant@host2 bitcamp-ncp]git merge
[vagrant@host2 bitcamp-ncp]git log --oneline --graph --all
[vagrant@host1 bitcamp-ncp]git pull
```

* git pull은 git fetch와 git merge를 합친 것이다.
* git을 만든 이가 최대한 branch를 사용하라고 하였다.
* 그만큼 많이 유용하다

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