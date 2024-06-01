# 오픈소스SW개론 과제

## top 
실시간으로 시스템의 프로세스와 자원 사용 현황을 모니터링하는데 사용하는 명령어
- `-d [seconds]`: 화면 갱신 주기를 설정한다.
- `-p [PID]`: 특정 PID 의 프로세스만 모니터링한다.
- `-u [user]`: 특정 사용자의 프로세스만 표시한다.
    ### Examples
    ```sh
    top
    top -d 2
    top -u root
    ```
    ### Prints
    |이름|설명|
    |---|---|
    |PID|프로세스의 식별 번호
    |USER|프로세스 소유자의 이름
    |PR, NI|프로세스 우선순위
    |VIRT, RES, SHR|프로세스가 사용하는 메모리 사용량
    |S|프로세스 상태
    |%CPU| CPU 사용률
    |%MEM|메모리 사용률
    |TIME+|프로세스가 사용한 총 CPU 시간
    |COMMAND|프로세스의 실행 명령행
    
# ps
현재 실행 중인 프로세스의 스냅샷을 출력할 때 사용하는 명령어
- `-e or -A`: 모든 프로세스를 출력한다.
- `-f`: 풀 포맷으로 출력한다.
- `-u [user]`: 특정 사용자의 프로세스를 출력한다.
- `-p [PID]`: 특정 PID의 프로세스를 출력한다.
    ### Examples
    ```sh
    ps -e
    ps -f
    ps -u username
    ps -p 1234
    ```
    ## Prints
    |이름|설명|
    | ------------- | ----------------
    |USER, USD|프로세스 소유자의 이름
    |PID|프로세스의 식별 번호
    |PPID|부모 프로세스의 PID
    |%CPU|CPU 사용 비율의 추정치
    |%MEM|Memory 사용 비율의 추정치
    |VSZ|K 단위 또는 페이지 단위의 가상 메모리 사용량
    |RSS|실제 메모리 사용량
    |TTY|프로세스와 연결된 터미널
    |S, STAT| 현재 프로세스의 상태 코드
    |TIME|총 CPU 사용 시간
    |COMMAND|프로세스의 실행 명령행
    |STIME| 프로세스가 시작된 시간 혹은 날짜 
    |C, CP| 짧은 기간 동안의 CPU 사용률       
    |F|플래그
    |PRI|실제 실행 우선순위
    |NI|nice 우선순위 번호
    
    
    
# kill
특정 프로세스에 시그널을 보내 종료시키거나 다른 동작을 유도하는 명령어
기본 시그널은 SIGTERM이다.
- `[Signal] [PID]`: 특정 시그널을 지정하여 프로세스를 제어한다.
    ### Examples
    ```sh
    kill 1234
    kill -9 1234  # 강제 종료 (SIGKILL)
    kill -HUP 1234  # 설정 재로딩 (SIGHUP)
    ```
    ### Prints
    따로 출력 형태는 정해져 있지 않다.

    ### Signals
    ![Assets](/assets/20240601.png)
