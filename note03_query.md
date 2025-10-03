# note03. 빅쿼리에서의 쿼리

- ARRAY와 STRUCT는 특히 BigQuery와 같은 최신 SQL 환경에서 중첩된 (Nested) 데이터를 다룰 때 유용하게 사용되는 데이터 타입

- unnest를 통해 nested 데이터 구조 flatten
    ~~~
    SELECT
    name, pref_lang, hometown
    FROM example_data
    CROSS JOIN UNNEST(preferred_language) AS pref_lang
    ~~~   

    <div style="display: flex; justify-content: space-between; gap: 10px;">
        <div style="width: 50%; text-align: center;">
            <img src="img/note03_img01.png" alt="그림1 설명" style="width: 100%; height: auto;">
            <p style="margin-top: 5px; font-style: italic; font-size: 0.9em;">unnest 전 데이터 포맷</p>
        </div>
        <div style="width: 50%; text-align: center;">
            <img src="img/note03_img02.png" alt="그림2 설명" style="width: 100%; height: auto;">
            <p style="margin-top: 5px; font-style: italic; font-size: 0.9em;">unnest 후 데이터 포맷</p>
        </div>
    </div>
