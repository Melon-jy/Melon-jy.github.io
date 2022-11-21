---
layout: post
title:  "리눅스VM 수업"
date:   2022-11-21 11:40:33 +0900
categories: jekyll update
---

# Vagrant project VS VirtureBox


* Host OS(windows OS) -> 사용자 -> 사용자 이름 폴더(home폴더)->VM-Project/
* host1-vm (VM 생성 프로젝트 폴더) / VagrantFile(설정-파일)
* Host OS->virtualBox VMs -> host1-vm_default...(VM 폴더) -> 내용물(VM 관련 파일)
* Vagrant Project(가상 머신을 만들고 초기화 시키는 설정 정보가 들어있는 프로젝트)
* VirtualBOX VM-> Vagrant 프로젝트에 따라 생성된 VM

```
사용자>host폴더>vm-project>centos1>vagrant destroy

```

# CVS vs SVN vs GIT




## CVS(Concurrent Versions System)중앙 집중 관리 시스템


* server Repo.(in Project file) <- check in(commit)Checkout File-> Local(프로젝트 파일)
* Check in - 최신 버전의 파일을 가져온다.
* commit시 파일을 모두 서버에 전송 -> Overhead 발생(과부하)-> network를 과다 사용 (변경내용 외에 기존 내용까지 전송하기 때문에)
* 서버에서 변경내역 관리 -> 중앙 집중 방식 -> 서버에 문제 발생시 변경 내역을 모두 잃음




## SVN(subversion) 중앙 집중 관리 시스템


* Commit(checkin)-> 파일의 변경 부분만 서버에 전송하기 때문에 CVS 방식 보다 Network Overhead가 적음
* 중앙 집중식이기 때문에 CVS와 마찬가지로 서버에 문제 발생될 경우 변경 내역을 모두 잃음




## Git(분산관리시스템)


* Git과 Github는 완전 다름 (커피와 카페 느낌)
* 서버에서 로컬로 Repo.를 똑같이 Clone함
* 로컬에서 서버로 Repo.를 똑같이 Push함
* 저장소를 클라이언트 쪽에 분산 복제가 가능함-> 서버에 문제가 발생하더라도 Client쪽에 분산 복제된 Repo.를 사용하여 원상태로 복원 가능함
* 변경 내역을 변경 후 Commit을 하게되면 로컬 Repo.에 저장됨
* 타인과의 공유가 필요할 경우에 서버에 Push를 하기에 Network Overhead가 적음




## RCS(Revision Control System)(CVS, SVN)


* RCS(Revision Control System) 는 개발자가 혼자 개발을 하여 관리할 경우 로컬 버전 관리 시스템을 사용함
* 버전 관리 시스템은 체크아웃을 할 경우 파일의 마지막 스냅샷(Snapshot)을 받는다.
* 스냅샷(snapshot)이란? 특정 시점의 파일 버전을 기록한 것.
* 로컬(local)은 한 개의 스냅샷만 유지한다.
* 만약 서버에 문제가 생기면 모든 내력(History)을 잃는다
* 로컬에 있는 스냅샷 중에서 최신 버전으로 복구한다.




## Git Local 저장소와 작업 디렉토리

* ~/git/bitcamp-study/.git/ = 로컬 저장소:변경내역이 들어있음 전송시 최신 스냅샷(Snapshot)의 파일을 꺼낸다
* ~/git/bitcamp-study/other/ <- 작업 디렉토리
* docs/, .gitignore, README.md = .git 저장소에서 꺼낸 파일 및 디렉토리
* 로컬 저장소는 git client가 관리하는 폴더, 사용자가 직접 편집하면 안됨
* 특정 버전의 Snapshot을 꺼낼 수 있다

## git 명령

```
 git config --system
 git config --global
 git config -l
 git config -list
 ```