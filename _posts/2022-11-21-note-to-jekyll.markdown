---
layout: post
title:  "리눅스VM 수업"
date:   2022-11-21 11:40:33 +0900
categories: jekyll update
---

## Vagrant project VS VirtureBox


### Host OS(windows OS) -> 사용자 -> 사용자 이름 폴더(home폴더)->VM-Project/
### host1-vm (VM 생성 프로젝트 폴더) / VagrantFile(설정-파일)
### Host OS->virtualBox VMs -> host1-vm_default...(VM 폴더) -> 내용물(VM 관련 파일)
### Vagrant Project(가상 머신을 만들고 초기화 시키는 설정 정보가 들어있는 프로젝트)
### VirtualBOX VM-> Vagrant 프로젝트에 따라 생성된 VM

```
사용자>host폴더>vm-project>centos1>vagrant destroy
```