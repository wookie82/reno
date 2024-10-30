# CVMFS

CVMFS(CernVM File System)는 고성능 컴퓨팅 환경에서 대규모 데이터 세트와 소프트웨어 애플리케이션을 효율적으로 관리하고 공유하기 위해 개발된 분산 파일 시스템입니다.&#x20;

이는 주로 대규모 연구 프로젝트와 데이터센터 등 에서 사용되며, 전 세계에 퍼져 있는 다수의 컴퓨터 클러스터에서 필요한 데이터에 빠르고 신뢰성 있게 접근할 수 있도록 설계되었습니다. CVMFS의 핵심 목표는 대용량 데이터의 중앙 집중화된 저장과 이를 필요로 하는 사용자들에게의 효율적인 배포입니다. 이는 특히 입자 물리학, 천문학, 생명 과학과 같은 데이터 집약적인 연구 분야에서 유용하게 활용됩니다. CVMFS는 읽기 전용의 설계로, 일단 데이터가 시스템에 저장되면, 전 세계 어디에서나 해당 데이터에 접근하여 사용할 수 있으나, 데이터의 변경은 중앙 집중적으로 관리되어 데이터의 무결성과 일관성을 유지합니다.



### CVMFS를 통한 gcc 사용하기

```
// CVMFS 에서 gcc 10.1 사용예제
$ which gcc
/usr/bin/gcc
$ source /cvmfs/sft.cern.ch/lcg/releases/LCG_98/gcc/10.1.0/x86_64-centos7/setup.sh
$ which gcc
/cvmfs/sft.cern.ch/lcg/releases/gcc/10.1.0-6f386/x86_64-centos7/bin/gcc
$

```



### CVMFS를 통한 ROOT 사용하기

```
// CVMFS에서 ROOT 사용예제 (gcc 10.1)
$ source /cvmfs/sft.cern.ch/lcg/views/LCG_100/x86_64-centos7-gcc10-opt/setup.sh
```
