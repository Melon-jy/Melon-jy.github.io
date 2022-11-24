---
layout: post
title:  "HTTP, CSS 수업"
date:   2022-11-24 09:30:33 +0900
categories: jekyll update
---


# CR / LF (Carriage Return / Line Feed)

* Carriage Return / Line Feed : 타자기에서 줄 바꾸는 것을 모방하여 만든 코드 값
* CR -> 0x0D
* LF -> 0x0A
* Windows OS 에서는 줄 바꿈을 표시할 때 CRLF 2byte를 붙인다.
* Unix/Lunux 에서는 줄 바꿈을 표시할 때 LF 1byte만 사용한다.
* HTML5는 끝맺음[/]를 생략해도 됨
```
[vagrant@host1 ~]$ ls
[vagrant@host1 ~]$ nano a.txt
[vagrant@host1 ~]$ ls -al
```

### HTML 기본 Tag

* hr = 선긋기
* a = 앵커 (닻)
* href = 하이퍼 텍스트 레퍼런스
* p = 줄바꿈 끝맺음/ 를 써야함
* br = 줄바꿈 끝맺음이 필요없음
* head, nav, body, footer = 위에서 부터 아래로
* h1~h6 = h1이 가장 크고 h6가 가장 작음
* id = 가장 위에 올려주는 것
* b = 볼드
* i = 이탤릭
* small = 작게
* sub = 밑으로
* sup = 위로
* ins = 아랫줄
* del = 취소선
* ruby = 부모태그
* rp = 작게 출력
* ol = ordered list
* ul = unordered list
* type = 종류 설정
* start = 시작점 설정
* li = 리스트
* dd = 디스크립션데이터  컨텐츠 내용
* dt = 디스크립션타이틀  컨텐츠 제목
* table =  테이블
* tr = 테이블 정렬
* th = 테이블 헤더
* td = 테이블 데이터
* tb = 테이블 바디
* tf = 테이블 하단
* caption
* thead style = 테이블 헤드 스타일
* tbody style = 테이블 바디 스타일
* tfooter style = 테이블 하단 스타일
* col = 컬러
* sapn = 칸수
* colgroup = 컬러 그룹 지정
```
<!---> 이렇게 하여 주석을 달아 태그를 정지할 수 있음
HTML 공부법 태그를 정지해서 하나씩 추가하고 지우면서 확인하기
```
* colspan="3" = 컬러 3칸을 합치겠다
* rowspan="3" = 로우 3칸을 합치겠다
* img = 이미지
* src = 소스
* alt = alt 속성 값을 보여주거나 속성이 없으면 소스를 보내줌 
* alt = 시각 장애인을 위해서라도 필요함
* width = 픽셀 단위의 넓이
* heigth = 필셀 단위의 높이
* audio = 오디오
```
<audio> src="kalimba.mp3" controls="controls"</audio>
```
* controls = 컨트롤 (값을 지정할 필요 없는 컨트롤
* selected = 고르기
* checked = 체크하기
* readonly = 읽기전용 
* autoplay = 자동재생 ) - 보안 정책상 자동으로 재생할 수 없음
* source = 소스 mp3를 재생할 수 없다면 ogg를 써야함

* MIME(Multi Purpose Internet Mail Extensions) 메일에 첨부한 컨텐츠가 어떤 형식인지 상대편에게 알려주는 용도 
* MIME type - 구글링 (mdn web docs / Developer.mozilla.org)
* Video = 비디오
```
video poster="지정 이미지/크기" = 썸네일
```
* select - 선택지가 많을때 사용하는 것
```
<option multiple size="7>
```
* 을 이용해 여러가지 선택을 할 수 있게 함


### Tag와 attribute

* a attribute="value">콘텐츠<끝태그
* Style : 끝맺음을 따로 해야함
* inline style : 최우선 순위으로 스타일을 value에 정함
* 외부 css 파일 :
* css링크 걸기 : link href="x.css"
* form : 
* input : 입력칸
* method : 
* name : 
* post : 
* password :
* submit : 
* text : 글을 쓸 수 있음
* button : valur="oo"/ 하면 oo가나옴
* checkbox : 체크박스가 생성됨 여러개를 만들 수도 있음 취소가 가능함
* file : 파일 선택
* hidden :
* image :
* radio : 체크박스 같은 것이 생기고 취소가 불가능함
```
<input type="radio" name="cf" /> = 
<input type="radio" name="cf" /> = 네임을 이렇게 같게 하면 셋중 하나는 선택해야함
<input type="radio" name="cf" checked/> = 기본 선택
```
* reset : 초기화
* label : 이름 달기
```
<label for=username">이름</label>
<input type="text" id="username" />
<input type=text" id="title" />
```
#### input

* type="color" - 
* type="datetime" - 
* type="datetime-local"
* type="month"
* type="number"
* type="range"
* type="cearch"
* type="tel"
* type="time"
* type="url"
* type="week"
* type="email"
```
핸드폰에서 숫자 키보드와
qwerty 키보드 나누려면 정확하게 type에 number를 줘야함
tel을 주면 키보드까지 올라옴
```
fieldset 필드 지정
legend 입력양식

* filedset
* legend 입력 양식
















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