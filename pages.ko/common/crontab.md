# crontab

> 현재 사용자의 시간 간격으로 cron작업이 실행되도록 스케줄.
> 작업 정의 형식: "(분) (시) (날짜) (달) (요일) 실행 할 명령".
> 더 많은 정보: <https://crontab.guru/>.

- 현재 사용자의 crontab파일 편집:

`crontab -e`

- 특정 사용자에 대한 crontab파일 편집:

`sudo crontab -e -u {{사용자}}`

- 현재 사용자의 기존 cron작업 목록 보기:

`crontab -l`

- 현재 사용자의 모든 cron작업 제거:

`crontab -r`

- 매일 10:00에 실행되는 샘플 작업 (* 은 모든 값을 의미 함):

`0 10 * * * {{실행_할_명령}}`

- 4월 3일에 1분마다 실행되는 샘플 작업:

`* * 3 Apr * {{실행_할_명령}}`

- 매주 금요일 02:30에 특정 스크립트를 실행하는 샘플 작업:

`30 2 * * Fri {{/script.sh/의/절대/경로}}`
