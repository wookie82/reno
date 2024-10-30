# 배치시스템, HTCondor 사용법



## 기본예제 1 : “Hello HTCondor”를 출력

```
$ vi helloworld.jds

executable = helloworld.sh
universe = vanillaoutput = helloworld.out
error = helloworld.errorlog = helloworld.log
should_transfer_files = YES
when_to_transfer_output = ON_EXIT
transfer_input_files = helloworld.sh
queue
```

```
$ vim helloworld.sh

#!/bin/bash
HELLO="Hello HTCondor"
echo $HELLO
```

```
$ condor_submit helloworld.jds
Submitting job(s).1 job(s) submitted to cluster 1.
```

```
$ condor_q

-- Schedd: XXXXXXXXXXXXXX : <XXX.XXX.XXX.XXX:XXXX?... @ XX/XX/XX XX:XX:XX
OWNER    BATCH_NAME    SUBMITTED   DONE   RUN IDLE  TOTAL JOB_IDS
example      ID: 1     5/16 21:53   _   1      _      1 1.0

Total for query: 1 jobs; 0 completed, 0 removed, 0 idle, 1 running, 0 held, 0 suspended
Total for bae: 1 jobs; 0 completed, 0 removed, 0 idle, 1 running, 0 held, 0 suspended
Total for all users: 1 jobs; 0 completed, 0 removed, 0 idle, 1 running, 0 held, 0 suspended

$
```

```
$ cat helloworld.out
Hello HTCondor
$
```



## 기본예제 2 : 작업시작, 완료된 시간 및 작업이 수행된 계산노드의 호스트네임 출력

```
$ vim time.jds

executable = time.sh
universe = vanilla
output = time_$(process).out
error = time_$(process).error
log = time_$(process).log
should_transfer_files = YES
when_to_transfer_output = ON_EXIT
transfer_input_files = time.sh
queue 14
```

```
$ vim time.sh#!/bin/bash
echo $(date)sleep 60
echo $(date)echo $(hostname)
```

```
$ condor_submit time.jds
Submitting job(s)..............
14 job(s) submitted to cluster 2.
[bae@group08-mn simple_test#2]$
```

```
$ condor_q

-- Schedd: xxxxxxxxxx.xx.xxxxxx : <xxx.xxx.xxx.xxx:xxx?... @ 05/17/23 00:40:39
OWNER    BATCH_NAME    SUBMITTED   DONE   RUN IDLE  TOTAL JOB_IDS
example      ID: 2     5/17 00:40   _   12      2     14 2.0-13
Total for query: 14 jobs; 0 completed, 0 removed, 2 idle, 12 running, 0 held, 0 suspended
Total for bae: 14 jobs; 0 completed, 0 removed, 2 idle, 12 running, 0 held, 0 suspended
Total for all users: 14 jobs; 0 completed, 0 removed, 2 idle, 12 running, 0 held, 0 suspended
$
```

```
$ cat time*.out
Thu May 17 00:40:38 PDT 2023
Thu May 17 00:41:38 PDT 2023
group08-wn03
Thu May 17 00:40:38 PDT 2023
Thu May 17 00:41:38 PDT 2023
group08-wn02
Thu May 17 00:40:39 PDT 2023
Thu May 17 00:41:39 PDT 2023
group08-wn02
Thu May 17 00:41:40 PDT 2023
Thu May 17 00:42:40 PDT 2023
group08-wn01
Thu May 17 00:41:40 PDT 2023
Thu May 17 00:42:40 PDT 2023
group08-wn02
Thu May 17 00:40:38 PDT 2023
Thu May 17 00:41:38 PDT 2023
group08-wn03
Thu May 17 00:40:38 PDT 2023
Thu May 17 00:41:38 PDT 2023
```

## 기본예제 3 : 1부터10000까지 합계 계산

```
$ vi hap.jdsexecutable = hap.shuniverse = vanilla
output = hap.outerror = hap.error
log = hap.log
should_transfer_files = YES
when_to_transfer_output = ON_EXIT
transfer_input_files = hap.sh
```

```
$ vim hap.sh

#!/bin/bash

hap=0
for i in {1..10000}
do
    hap=$(expr $hap + $i)
done
echo "1 to 10000 hap: " $hap
```

```
$ condor_submit hap.jds
Submitting job(s).1 job(s) submitted to cluster 3.
$
```

```
$ condor_q

-- Schedd: xxxxxxxxx.xxxxxx.xxxxxxx : <xxx.xxx.xxx.xxx:9618?... @ 05/16/23 23:18:29
OWNER    BATCH_NAME    SUBMITTED   DONE   RUN IDLE  TOTAL JOB_IDS
bae      ID: 3     5/16 23:18   _   1      _      1 3.0
Total for query: 1 jobs; 0 completed, 0 removed, 0 idle, 1 running, 0 held, 0 suspended
Total for bae: 1 jobs; 0 completed, 0 removed, 0 idle, 1 running, 0 held, 0 suspended
Total for all users: 1 jobs; 0 completed, 0 removed, 0 idle, 1 running, 0 held, 0 suspended
$
```

```
$ cat hap.out

1 to 10000 hap:  50005000
$
```
