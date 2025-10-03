# note02. 앱로그 데이터 특징

1. Event
    - 사용자 행동(클릭, 페이지뷰)
    - 구성
        - key: 이벤트 파라미터
        - value: 이벤트 파라미터 값
    - 파라미터명
        - screen_view
        - click_...
3. 로그 설계
    - 참고. [로그설계 블로그 글](https://zzsza.github.io/data/2021/06/13/data-event-log-definition/)
    - 로그 설계 따라 GA4, Firebase에서 쿼리 사용 가능
    - 앱로그 파일 확장자: orc
        - csv보다 용량 작음
        - 배열, 스트럭트 구조 같은 복잡한 구조 표현 가능
3. 데이터셋 업로드
    - 데이터 세트 만들기 -> 테이블 만들기
        - orc 확장자 파일 업로드
    - 데이터 파티션 설정
        ~~~
        CREATE OR REPLACE TABLE advanced.app_logs PARTITION BY event_date
        AS
        SELECT
        *
        FROM advanced.app_logs_temp
        ~~~
        
