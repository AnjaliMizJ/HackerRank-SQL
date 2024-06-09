<h1>Prblem 1: </h1>

Pivot the Occupation column in OCCUPATIONS so that each Name is sorted alphabetically and displayed underneath its corresponding Occupation. The output column headers should be Doctor, Professor, Singer, and Actor, respectively.

**Note:** Print NULL when there are no more names corresponding to an occupation.

**Input Format**

The OCCUPATIONS table is described as follows:
![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/c2d50c1c-1a75-422f-9fbc-4c9d38adb57f)

Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

**Sample Input**
![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/9b984e13-75b1-49b5-a754-f5ca0f3e5cd6)

**Sample Output**

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/977ac48a-bb1c-4eea-aea1-a92085dfdaba)

The first column is an alphabetically ordered list of Doctor names.
The second column is an alphabetically ordered list of Professor names.
The third column is an alphabetically ordered list of Singer names.
The fourth column is an alphabetically ordered list of Actor names.
The empty cell data for columns with less than the maximum number of names per occupation (in this case, the Professor and Actor columns) are filled with **NULL** values.

<h3>Solution: </h3>

SELECT

    MAX(Doctor) AS Doctor,
    
    MAX(Professor) AS Professor,
    
    MAX(Singer) AS Singer,
    
    MAX(Actor) AS Actor
    
FROM (

    SELECT
    
        CASE WHEN Occupation = 'Doctor' THEN Name END AS Doctor,
        
        CASE WHEN Occupation = 'Professor' THEN Name END AS Professor,
        
        CASE WHEN Occupation = 'Singer' THEN Name END AS Singer,
        
        CASE WHEN Occupation = 'Actor' THEN Name END AS Actor,
        
        ROW_NUMBER() OVER (PARTITION BY Occupation ORDER BY Name) AS rn
        
    FROM OCCUPATIONS
    
) AS temp

GROUP BY rn

ORDER BY rn;
