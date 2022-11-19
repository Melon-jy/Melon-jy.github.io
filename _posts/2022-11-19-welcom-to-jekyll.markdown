---
layout: post
title:  "비트캠프 과제2"
date:   2022-11-19 00:15:30 +0900
categories: jekyll update
---

<span style="font-size:30px;">하이퍼바이저 자기주도 학습하기</span>

1. 과제물 인터넷+컴퓨터or노트북or핸드폰

2. 구글링 혹은 네이버 검색창에 hypervisor 혹은 하이퍼바이저에 대한 검색

저는 https://dora-guide.com/%ED%95%98%EC%9D%B4%ED%8D%BC%EB%B0%94%EC%9D%B4%EC%A0%80/ 이곳에서 할 예정입니다.<br><br><br>

<span style="font-size:24px;">
하이퍼바이저(hypervisor)란 호스트 컴퓨터에서 다수의 OS를 동시에 실행하기 위한 논리적 플랫폼을 말합니다.
virtual machine monitor이나 Virtual machine manager이며 약어로 VMM이라 합니다.
하이퍼바이저는 게스트 운영 체제에 가상 운영 플랫폼을 제공하면서 게스트 운영 체제를 관리합니다. 다양한 운영 체제의 여러 인스턴스가 가상화된 하드웨어 리소스를 공유할 수 있습니다.ex) Linux, windows, Mac OS 인스턴스는 모두 단일 물리적 x86 시스템에서 실행될 수 있습니다.

하이퍼바이저 목차
1. 하이퍼바이저의 역사
2. 하이퍼바이저 유형
3. 컨테이너와 하이퍼바이저
4. 하이퍼바이저 보안 문제

**역사**

1960년에서 1970년까지 대부분의 가상화 및 하이퍼바이저 작업은 IBM이 개발한 메인 프레임 컴퓨터에서 시분할 시스템(Time-sharing)을 구축, 새로운 운영체제 아이디어 테스트 또는 새로운 하드웨어 개념 탐색에서 사용됨.
가상화 측면을 통해 프로그래머는 주요 프로덕션 시스템의 안정성을 해치지 않고 추가 비용이 드는 개발 시스템을 배포하지 않고도 배포 및 디버깅할 수 있었습니다.

2000년대 중반으로 넘어가면서 파이퍼바이저는 Linux및 기타 Unix와 같은 OS 체제가 가상화 기술을 활용하기 시작했을 때 활성화 되었고 하이퍼 바이저 및 가상화의 성장 이유에는 더 나은 하드웨어 기능이 포함되어 단일 시스템에서 더 많은 동시작업이 가능해졌습니다.

서버 통합으로 이어진 비용 관리, 하이퍼 바이저 아키텍처 개선으로 인한 보안 및 안정성 향상 다른 하드웨어 또는 OS 환경에서 OS 종속 응용 프로그램을 실행할 수 있었으며 또한 2005년에 CPU공급 업체는 x86 기반 제품에 하드웨어 가상화를 추가하여 가상화의 가용성을 PC 및 서버 기반 대상으로 확대했습니다.

**하이퍼바이저의 유형**

하이퍼바이저에는 유형1 또는 유형2 두 가지 유형의 하이퍼 바이저가 있습니다."Native"또는 "Bare-metal" 하이퍼바이저라고도 하는 유형1 하이퍼 바이저는 호스트 하드웨어에서 직접 실행되어 하드웨어를 제어하고 게스트 가상머신을 관리합니다.

<img src="https://github.com/Melon-jy/Melon-jy.github.io/blob/main/Type1.jpg?raw=true" width="400">

유형1의 주요 이점은 가상 시스템 또는 게스트 운영 체제 중 하나의 문제가 하드웨어에서 실행중인 다른 게스트 운영체제에 영향을 미치지 않는다는 것입니다.

유형1 하이퍼바이저에는 대표적으로 Xen, Oracle VM server for SPARC, Oracle VM server for x86, Microsoft Hyper-V 및 VMware의 ESX/ESXi가 있습니다.

<img src="https://github.com/Melon-jy/Melon-jy.github.io/blob/main/Type2.jpg?raw=true" width="400">

호스트 된 하이퍼바이저라고도 하는 유형2 하이퍼바이저는 시스템의 다른 응용 프로그램과 마찬가지로 일반적인 OS에서 실행되며 이 경우 게스트 OS는 호스트에서 프로세스로 실행되는 반면 하이퍼바이저는 게스트 OS와 호스트 OS를 분리합니다.

또한 운영에 있어 호스트 운영 체제에 전적으로 의존합니다. 기본 운영 체제에서 실행되는 하이퍼바이저가 안전하더라도 기본 운영체제의 모든 문제는 전체 시스템에 영향을 줍니다.

유형2 하이퍼바이저는 VMware Workstation, VMware Player, VirtualBox 및 Parallels Desktop for Mac이 있습니다.

**컨테이너(container)와 하이퍼바이저(Hypervisor)**

최근 컨테이너 기술은 가상머신보다 단일 물리적 서버에 더 많은 APP를 배치할 수 있기 때문에 하이퍼바이저를 대체할 수 있는 가능성으로 인기를 얻고 있으며

컨테이너형 가상화 기술은 기존의 가상화 기술보다 가벼워지고, 이식성이 뛰어납니다. 대표적인 컨테이너 기술로는 docker가 있습니다. 컨테이너는 가상 머신보다 공간을 덜 차지하며, 더 많은 응용 프로그램을 처리할 수 있습니다.

그러나 보안 문제와 가상 머신의 실제 사용자들은 컨테이너가 하이버파이저/가상머신을 반드시 대체 할 필요가 없으며, 이 두 가지 모두 혼용하여 사용하는 것이 더 좋다고 말합니다.

보안 문제에서 일부 사람들은 컨테이너가 으용 프로그램이 공유하는 OS가 하나만 있고 가상 머신이 응용 프로그램뿐 아니라 OS도 격리하기 때문에 컨테이너가 하이퍼바이저 보다 덜 안전하다고 생각합니다.

그러나 응용 프로그램이 손상되면 컨테이너의 단일 OS를 공격하여 다른 응용 프로그램에 영향을 줄 수 있습니다. 가상 머신의 으용ㅇ 프로그램이 손상되면 해당 서버의 한 OS만 영향을 받고 다른 응용 프로그램이나 OS는 영향을 받지 않습니다.

**하이퍼바이저 보안 문제**

하이퍼바이저가 일부 조치에 의해 컨테이너보다 더 안전한 것으로 간주될 수도 있지만 하이퍼 바이저와 관련된 보안 문제가 없는 것은 아닙니다. 이론상 해커는 OS 아래에 하이퍼바이저로 설치되는 멀웨어 및 루트킷을 만들 수 있습니다.

멀웨어가 OS아래에서 실행되기 때문에 멀웨어 방지 소프트웨어가 감지하지 않으면서 멀웨어가 OS작동(ex:암호 입력)을 가로챌 수 있기 때문에 하이퍼 재킹으로 알려진 이 프로세스를 탐지하기가 더 어려울 수 있습니다.</span>


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