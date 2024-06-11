Amber's conglomerate corporation just acquired some new companies. Each of the companies follows this hierarchy: 

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/5d05ad0d-7a3d-41c9-8a36-d4bfe3e207a4)


Given the table schemas below, write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.

**Note:**

- The tables may contain duplicate records.

- The company_code is string, so the sorting should not be numeric. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes will be C_1, C_10, and C_2.

**Input Format**

The following tables contain company data:

**Company:** The company_code is the code of the company and founder is the founder of the company. 

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/bf2c5116-a9d2-49ab-94fd-c88ec9b4ac6d)

**Lead_Manager:** The lead_manager_code is the code of the lead manager, and the company_code is the code of the working company.

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/18c9ad62-231e-4a55-b318-305e99b96e8e)


**Senior_Manager:** The senior_manager_code is the code of the senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company. 

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/3a0da3e8-bb17-4fa5-9883-a139382a4790)

**Manager:** The manager_code is the code of the manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company. 

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/61990306-15bf-4946-8966-af8f3fe5f305)  

**Employee:** The employee_code is the code of the employee, the manager_code is the code of its manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company. 

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/73fe7632-e5b6-473c-a46e-398b7dc143c8)

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/a08d9e2e-be39-4c5d-9b93-416f3542f4b2)

**Solution**

  SELECT C.company_code, C.founder,
  
            COUNT(DISTINCT LM.lead_manager_code),
            
            COUNT(DISTINCT SM.senior_manager_code),
            
            COUNT(DISTINCT M.manager_code),
            
            COUNT(DISTINCT E.employee_code)
            
  FROM company  C, lead_manager  LM,
  
            senior_manager  SM, manager  M, employee  E
            
  WHERE C.company_code=LM.company_code AND
  
            LM.lead_manager_code=SM.lead_manager_code AND
            
            SM.senior_manager_code=M.senior_manager_code AND
            
            M.manager_code=E.manager_code
            
  GROUP BY C.company_code, C.founder
  
  ORDER BY C.company_code 

  


