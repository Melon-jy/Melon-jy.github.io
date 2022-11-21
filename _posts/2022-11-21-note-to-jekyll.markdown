---
layout: post
title:  "리눅스VM 수업"
date:   2022-11-21 11:40:33 +0900
categories: jekyll update
---

# Vagrant project VS VirtureBox


### Host OS(windows OS) -> 사용자 -> 사용자 이름 폴더(home폴더)->VM-Project/
### host1-vm (VM 생성 프로젝트 폴더) / VagrantFile(설정-파일)
### Host OS->virtualBox VMs -> host1-vm_default...(VM 폴더) -> 내용물(VM 관련 파일)
### Vagrant Project(가상 머신을 만들고 초기화 시키는 설정 정보가 들어있는 프로젝트)
### VirtualBOX VM-> Vagrant 프로젝트에 따라 생성된 VM

```
사용자>host폴더>vm-project>centos1>vagrant destroy

```

# CVS vs SVN vs GIT

## CVS(Concurrent Versions System)중앙 집중 관리 시스템
### server Repo.(in Project file) <- check in(commit)Checkout File-> Local(프로젝트 파일)
### Check in - 최신 버전의 파일을 가져온다.
### commit시 파일을 모두 서버에 전송 -> Overhead 발생(과부하)-> network를 과다 사용 (변경내용 외에 기존 내용까지 전송하기 때문에)
### 서버에서 변경내역 관리 -> 중앙 집중 방식 -> 서버에 문제 발생시 변경 내역을 모두 잃음

## SVN(subversion) 중앙 집중 관리 시스템
### Commit(checkin)-> 파일의 변경 부분만 서버에 전송하기 때문에 CVS 방식 보다 Network Overhead가 적음
### 중앙 집중식이기 때문에 CVS와 마찬가지로 서버에 문제 발생될 경우 변경 내역을 모두 잃음

## Git(분산관리시스템)
### Git과 Github는 완전 다름 (커피와 카페 느낌)
### 서버에서 로컬로 Repo.를 똑같이 Clone함
### 로컬에서 서버로 Repo.를 똑같이 Push함
### 저장소를 클라이언트 쪽에 분산 복제가 가능함-> 서버에 문제가 발생하더라도 Client쪽에 분산 복제된 Repo.를 사용하여 원상태로 복원 가능함
### 변경 내역을 변경 후 Commit을 하게되면 로컬 Repo.에 저장됨
### 타인과의 공유가 필요할 경우에 서버에 Push를 하기에 Network Overhead가 적음

## RCS(Revision Control System)(CVS, SVN)
### RCS(Revision Control System) 는 개발자가 혼자 개발을 하여 관리할 경우 로컬 버전 관리 시스템을 사용함
### 버전 관리 시스템은 체크아웃을 할 경우 파일의 마지막 스냅샷(Snapshot)을 받는다.