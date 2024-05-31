# top
+ 실시간으로 시스템의 프로세스와 기타 시스템 정보를 보여준다.
+ CPU와 메모리 사용량, 실행중인 프로세스 목록 등을 실시간으로 모니터링 할 수 있다.
+ ### 사용법
  ```bash
  top [옵션]
  ```
+ ### 주요 옵션
  + '-d <interval>' : 업데이트 간격을 초 단위로 설정
  + '-p <PID>' : 특정 PID의 프로세스만 모니터링
  + '-n <number>' : 지정한 횟수만큼 업데이트 후 종료
  + '-u <username>' : 특정 사용자의 프로세스만 표시
  + '-b' : 배치 모드로 실행하여 출력 결과를 표준 출력으로 보냄
  + '-c' : 명령어 라인/ 프로그램 이름을 토글
  + '-i' : 유휴 및 좀비 프로세스 무시
  + '-H' : 각 프로세스의 스레드를 별도로 표시
  + '-s' : 보안 모드를 활성화 하여 키보드 입력을 비활성화
  + '-o <field>' : 지정한 필드로 정렬
 
+ ### Interactive 모드에서의 주요 키
  'top' 명령어는 실행 중에도 다양한 키를 통해서 인터페이스를 제어할 수 있음
  + 'P' : CPU 사용량 기준으로 정렬
  + 'M' : 메모리 사용량 기준으로 정렬
  + 'N' : PID 기준으로 정렬
  + 'T' : 실행 시간을 기준으로 정렬
  + 'k' : 특정 프로세스를 종료. PID를 입력하고 시그널을 지정함
  + 'r' : 특정 프로세스의 우선순위를 변경. PID와 새로운 nice값을 입력
  + 'q' : 'top' 명령어를 종료
  + 'h' : 도움말을 표시
---

# ps
+ 현재 실행중인 프로세스를 보여준다.
+ 다양한 옵션을 사용하여 프로세스의 상세 정보를 확인할 수 있다.
+ ### 사용법
  ```bash
  ps [옵션]
  ```
+ ### 주요 옵션
  + '-e' : 모든 프로세스를 표시
  + '-f' : 풀 포맷으로 출력
  + '-u' : 특정 사용자의 프로세스를 표시
  + '-p' : 특정 PID의 프로세스를 표시
  + '-a' : 터미널에 종속되지 않는 모든 프로세스를 표시
  + '-aux' : BSD 스타일로 모든 프로세스를 표시
  + '--sort <key>' : 지정한 key로 정렬
+ ### 주요 필드 설명
  + 'PID' : 프로세스 ID
  + 'TTY' : 터미널 타입
  + 'TIME' : CPU 사용 시간
  + 'CMD' : 실행된 명령
---

# jobs
+ 현재 쉘 세션에서 실행 중인 백그라운드 작업의 목록을 보여준다.
+ 작업 번호와 상태를 확인할 수 있다.
+ ### 사용법
  ```bash
  jobs [옵션]
  ```
+ ### 주요 옵션
 + '-l' : 프로세스 ID를 포함한 작업의 상세 정보를 표시
 + '-n' : 마지막으로 중지되거나 종료된 작업을 표시
 + '-p' : 각 작업의 프로세스 ID만 표시
 + '-r' : 현재 실행 중인 작업만 표시
 + '-s' 중지도니 작업만 표시

+ ### 작업 상태
  + 'Running' : 작업이 실행 중
  + 'Stopped' : 작업이 중지 됨
  + 'Done' : 작업이 완료 됨
  + 'Exited' : 작업이 종료 됨

+ ### 주요 사용 사례
 + 백그라운드 작업을 시작하려면 명령어 끝에 '&'를 붙임
 + 'fg' 명령어를 사용하여 백그라운드 작업을 포그라운드로 가져 올 수 있음
 + 'bg' 명령어를 사용하여 중지된 작업을 백그라운드에서 재개할 수 있
---

# kill
+ 특정 프로세스를 종료하는데 사용된다.
+ 주로 프로세스 ID(PID)를 사용하여 프로세스를 지정한다.
+ ### 사용법
  ```bash
  kill [옵션] <PID>`
  ```
+ ### 주요 옵션
  + 'l' : 사용 가능한 시그널 목록을 출력
  + '-s' : 보낼 시그널을 지정
  + '-L' : 사용 가능한 시그널을 테이블 형식으로 출력
  + '-p' : 프로세스 ID를 지정하지 않고 시그널을 보냄
+ ### 주요 시그널
  + '-1' : 프로세스를 재시작
  + '-9' : 강제 종료(SIGKILL)
  + '-15' : 정상 정료(SIGTERM, 기본값)
  + '-18' : 중지된 프로세스를 계속 실행
  + '-19: 프로세스를 중지

