![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/fec2dcf9-c04a-42c5-9b39-43d4d6ac832c)

Solution:

  SELECT ROUND(SQRT(POWER(MAX(LAT_N)-MIN(LAT_N),2)+POWER(MAX(LONG_W)-MIN(LONG_W),2)),4)
  FROM STATION;
