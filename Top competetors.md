
![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/89deea14-52a3-408d-a0af-f7a63e895198)


![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/8f808b3a-bae4-427b-bd91-550f10ad1f95)


![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/23b44ae3-0ac5-491d-98c9-cf4e7125450a)


![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/8050c5eb-156f-4f2c-bd48-810e16391bc1)


![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/c398cb29-2d9b-44b2-85fd-2cb06a20b35e)

***Solution:***
  SELECT H.hacker_id, 
   H.name 
FROM   submissions S 
   JOIN challenges C 
     ON S.challenge_id = C.challenge_id 
   JOIN difficulty D 
     ON C.difficulty_level = D.difficulty_level 
   JOIN hackers H 
     ON S.hacker_id = H.hacker_id 
        AND S.score = D.score 
GROUP  BY H.hacker_id, 
  H.name 
HAVING Count(S.hacker_id) > 1 
ORDER  BY Count(S.hacker_id) DESC,  S.hacker_id ASC;






