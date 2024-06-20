![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/bd509884-9444-4428-ac61-49df38215dfe)

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/a4cdcc86-e63e-4216-9a9b-1e71e64648c9)

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/94dd2f3d-0086-4fe9-95bc-bc36d9034b5c)


![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/bb71e405-36d7-4614-8c18-c951edeec280)





***solution:**

    SELECT a.id, 
   b.age, 
   a.coins_needed, 
   a.power 
  FROM   wands a 
   JOIN wands_property b 
     ON a.code = b.code 
  WHERE  b.is_evil = 0 
      AND a.coins_needed = (SELECT Min(a1.coins_needed) 
      FROM   wands a1 
          JOIN wands_property b1 
            ON a1.code = b1.code 
      WHERE  b.age = b1.age 
          AND a.power = a1.power) 
  ORDER  BY a.power DESC, 
          b.age DESC;
