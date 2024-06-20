![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/29bb455a-287a-4e4f-b906-c78569b6acea)

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/295647db-9383-4498-a56d-2365825c19ad)

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/f8b3a16e-aaf7-486e-ab8e-5b35021a2364)

**Solution:**

    SELECT CASE
      WHEN G.grade > 7 THEN S.name
      ELSE NULL
      end AS names,
      G.grade,
      S.marks
    FROM   students S
      JOIN grades G
      ON S.marks BETWEEN G.min_mark AND G.max_mark
    ORDER  BY G.grade DESC,
      names ASC,
      S.marks ASC;


