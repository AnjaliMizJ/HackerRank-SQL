You are given a table, BST, containing two columns: N and P, where N represents the value of a node in Binary Tree, and P is the parent of N.

![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/67fa8daa-0e89-4d2e-a47e-5c59859e1a75)

Write a query to find the node type of Binary Tree ordered by the value of the node. Output one of the following for each node:

- Root: If node is root node.

- Leaf: If node is leaf node.

- Inner: If node is neither root nor leaf node.
  
**Sample Input**
![image](https://github.com/AnjaliMizJ/HackerRank-SQL/assets/31090029/15fdbb38-4c58-4b35-a080-38333002760a)

**Solution**

  
              SELECT N, IF(P=NULL, "ROOT", 

                        IF((SELECT COUNT(*) FROM BST WHERE P=B.N)>0, "INNER","LEAF")) 
                        
              FROM BST AS B ORDER BY N

