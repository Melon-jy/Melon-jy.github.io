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

## Fast-Forward

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

### Fast Forward가 발생하지 않는 경우

* 작업중인 것이 있을 경우엔 git pull이 불가능
```
[vagrant@host1 bitcamp-ncp]git pull
[vagrant@host2 bitcamp-ncp]git pull
[vagrant@host1 bitcamp-ncp]git log --oneline --graph --all
[vagrant@host2 bitcamp-ncp]git log --oneilne --graph --all
[vagrant@host1 bitcamp-ncp]nano a.txt
[vagrant@host2 bitcamp-ncp]nano a.txt
[vagrant@host1 bitcamp-ncp]git add .
[vagrant@host1 bitcamp-ncp]git commit -m "22"
[vagrant@host1 bitcamp-ncp]git push
[vagrant@host2 bitcamp-ncp]git add .
[vagrant@host2 bitcamp-ncp]git commit -m "23"
[vagrant@host2 bitcamp-ncp]git push
[vagrant@host1 bitcamp-ncp]nano a.txt
[vagrant@host1 bitcamp-ncp]git add .
[vagrant@host1 bitcamp-ncp]git commit -m "24"
[vagrant@host1 bitcamp-ncp]git push
[vagrant@host2 bitcamp-ncp]git pull
[vagrant@host1 bitcamp-ncp]git log --oneline --graph --all
[vagrant@host2 bitcamp-ncp]git log --oneline --graph --all
```
* 오류부터 오류 수정까지 내용.
* 서로 같은 파일을 동시에 push 할 경우 두 기록이 모두 저장되며 직접 a.txt 파일로 들어가 어느 것을 어떻게 수정할 것인지 수작업으로 직접 편집할 수 있고 편집 이후 다시 commit하여 충돌이 일어난 부분을 해결할 수 있음
* 만약 이러한 기능이 없었더라면 1 2 3 4 5인의 사람이 같은 파일을 서로 다른 작업을 했을때 타인의 정보가 날아갈 수도 있지만 그러한 부분을 막아주며 동시에 수정을 하더라도 되돌릴 수 있는 프로그램이기 때문에 아주아주아주 효율적이며 아주아주아주 매력적인 기능
* merge시 충돌이 일어났다면 충돌이 일어난 부분을 확인한 후 편집한 다음 add . commit 하고 push pull

### 개발하는 동안 사용할 git Branch

* HEAD의 등장 - 현재 작업 중인 Branch를 가르킨다
* 다음 명령어로 새 Branch를 생성하고 삭제한다.

```
[vagrant@host1 bitcamp-ncp]git branch
[vagrant@host1 bitcamp-ncp]git branch b1
[vagrant@host1 bitcamp-ncp]git branch
[vagrant@host1 bitcamp-ncp]git log --oneline
[vagrant@host1 bitcamp-ncp]git branch -d b1
[vagrant@host1 bitcamp-ncp]git branch
[vagrant@host1 bitcamp-ncp]git log --oneline
```

### Branch CheckOut하기

* b1 branch를 생성 후 b1 branch를 checkout하여 HEAD가 b1 branch를 가르키게 하기.
* 24번 과정을/bitcamp-ncp/.git/ 에서 bitcamp-ncp/로 작업 디렉토리를 꺼냈을때
* git checkout b1 명령어를 줄 경우 HEAD가 main에서 b1으로 바뀜
* 그럴 경우 main에서 꺼낸 것은 다 삭제되고 b1에서 나온 디렉토리로 다시 꺼냄
* 그 branch의 마지막 버전 혹은 특정 버전을 꺼낼 수 있음[#코드를 입력할 경우]

```
[vagrant@host1 bitcamp-ncp]git branch b1
[vagrant@host1 bitcamp-ncp]git checkout b1
[vagrant@host1 bitcamp-ncp]git branch
[vagrant@host1 bitcamp-ncp]git log --oneline
[vagrant@host1 bitcamp-ncp]ls
[vagrant@host1 bitcamp-ncp]rm -d a.txt
[vagrant@host1 bitcamp-ncp]nano c.txt
[vagrant@host1 bitcamp-ncp]git checkout main
[vagrant@host1 bitcamp-ncp]ls
```

### branch - merge

* 현재 branch의 commit을 다른 branch의 commit에 합치는 것
* 27번이 생기지 않는 이유는 main의 24번은 b1의 분기 이후에 변경된 적이 없어, b1브랜치의 버전을 main 24번 이후에 그대로 이어 붙혀도 문제가 되지 않는다.
* 새로운 napshot을 만들지 않는다.
* 한번 main과 합친경우 새로 생성한 브랜치를 지우고 새로 만들어서 작업해야 충돌이 안남


```
[vagrant@host1 bitcamp-ncp]git checkout main
[vagrant@host1 bitcamp-ncp]git merge b1
[vagrant@host1 bitcamp-ncp]git branch -d b1
[vagrant@host1 bitcamp-ncp]git branch
[vagrant@host1 bitcamp-ncp]git log --oneline
```
* 새로 생성한 브랜치는 작업 이후 pull 하고 삭제 후 다시 생성해서
* 
* 

```
[vagrant@host2 bitcamp-ncp]git branch x1
[vagrant@host2 bitcamp-ncp]git checkout x1
[vagrant@host2 bitcamp-ncp]git branch
[vagrant@host2 bitcamp-ncp]nano x.txt
[vagrant@host2 bitcamp-ncp]git add .
[vagrant@host2 bitcamp-ncp]git commit -m "41"
[vagrant@host2 bitcamp-ncp]nano x.txt
[vagrant@host2 bitcamp-ncp]git add .
[vagrant@host2 bitcamp-ncp]git commit -m "42"
[vagrant@host2 bitcamp-ncp]git checkout main
[vagrant@host2 bitcamp-ncp]git merge x1
[vagrant@host2 bitcamp-ncp]git log --oneline
[vagrant@host2 bitcamp-ncp]git pull
[vagrant@host2 bitcamp-ncp]git push
[vagrant@host2 bitcamp-ncp]git branch -d x1
[vagrant@host2 bitcamp-ncp]git branch
```

## git 작업 순서

* server main branch(1) -> clone in local -> local main branch(1) -> branch생성 -> (2) -> (3) -> main branch로 merge -> 결과 확인
* server main branch(1) -> (21) -> (22) -> (23) -> pull -> local merge (24) -> server에 push -> server와 local에 결과 확인 후 branch 삭제



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