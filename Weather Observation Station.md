![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/11c8786c-c689-4b9d-b967-b4d42d6b2007)

**Solution:**

    SELECT ROUND(ABS(MIN(LAT_N) - MAX(LAT_N)  +
                MIN(LONG_W) -MAX(LONG_W)),4)
    FROM STATION

