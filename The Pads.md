Generate the following two result sets:

Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).
Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:

There are a total of [occupation_count] [occupation]s.
where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.

Note: There will be at least two entries in the table for each type of occupation.

Input Format

The OCCUPATIONS table is described as follows:

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/b28a3e7d-9374-4b5c-9a31-9c1af1e0809a)

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/636c426a-069d-4aff-bbc5-9243da0c4f34)

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/b1009141-ad5e-4933-8c81-45ca3622108f)

**Solution:**

  SELECT CONCAT(NAME,'(',SUBSTR(OCCUPATION,1,1),')') AS N
  
  FROM OCCUPATIONS

  ORDER BY N;
  
  SELECT CONCAT('There are a total of ',COUNT(OCCUPATION),' ',LOWER(OCCUPATION),'s.')

  FROM OCCUPATIONS
  
  GROUP BY OCCUPATION
  
  ORDER BY COUNT(OCCUPATION), OCCUPATION;



